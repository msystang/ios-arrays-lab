# Arrays lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.

## Question 1

Create an array of strings called `colors` that contain "orange", "red", "yellow", "turquoise", and "lavender".

Then, using array subscripting and string interpolation, print out the String `"orange, yellow, and lavender are some of my favorite colors"`.

Answer:
```swift
var colors = ["orange","red","yellow","turqoise", "lavender"]

print("\(colors[0]), \(colors[2]), and \(colors[4]) are some of my favorite colors")
```

## Question 2

Remove "Illinois" and "Kansas" from the array below.

`var westernStates = ["California", "Oregon", "Washington", "Idaho", "Illinois", "Kansas"]`

Answer:
```swift
var westernStates = ["California", "Oregon", "Washington", "Idaho", "Illinois", "Kansas"]
let illinois = "Illinois"
let kansas = "Kansas"
var newStates: [String]  = []

for state in westernStates {
if state == illinois || state == kansas {
continue
}
newStates.append(state)
}
print(newStates)
```

## Question 3

Iterate through the array below. For each state, print out the name of the state, a colon, and whether it is or is not **in the continental United States.**

`let moreStates = ["Hawaii", "New Mexico", "Alaska", "Montana", "Texas", "New York", "Florida"]`

Answer:
```swift
let moreStates = ["Hawaii", "New Mexico", "Alaska", "Montana", "Texas", "New York", "Florida"]

let hawaii = "Hawaii"
let alaska = "Alaska"

for state in moreStates {
if state == hawaii || state == alaska {
print("\(state): IS NOT in the continental United States.")
} else {
print("\(state): IS in the continental United States.")
}
}
```

## Question 4

Print out how many non-whitespace characters are in `myString`:

`let myString = "This is good practice with Strings!"`

Answer:
```swift
let myString = "This is good practice with Strings!"
let space = " "
var myStringNoSpace = ""

for character in myString {
if String(character) == space {
continue
} else {
myStringNoSpace += String(character)
}
}
print(myStringNoSpace.count)
```

Iterate through the array below. For each sentence, print out how many non-whitespace characters are in it.

`let myFavoriteQuotes = ["To be or not to be, that is the question.", "The only source of knowledge is experience.", "Mr. Gorbachev, tear down this wall!", "Four score and twenty years ago..."]`

Answer:
```swift
let myFavoriteQuotes = ["To be or not to be, that is the question.", "The only source of knowledge is experience.", "Mr. Gorbachev, tear down this wall!", "Four score and twenty years ago..."]
let space = " "
var myStringNoSpace = ""

outer: for quote in myFavoriteQuotes {
inner: for character in myFavoriteQuotes {
if String(character) == space {
continue
} else {
myStringNoSpace += String(character)
}
}
print("'\(quote)' has \(quote.count) non-whitespace characters in it.")
}
```

## Question 5

Iterate through `garden` and place any 🌷 that you find into the `basket`. Replace any 🌷 that you pick up with `"dirt"`. Then print how many 🌷 are in your `basket`.

```swift
var garden = ["dirt","🌷","dirt","🌷","dirt","dirt","🌷","dirt","🌷","dirt"]
var basket = [String]()
```

Answer:
```swift
var garden = ["dirt","🌷","dirt","🌷","dirt","dirt","🌷","dirt","🌷","dirt"]
var basket = [String]()
let flower = "🌷"
let dirt = "dirt"

for (index, plot) in garden.enumerated() {
if plot == flower {
basket.append(plot)
garden[index] = "dirt"
}
plot.replacingOccurrences(of: flower, with: dirt)
}

print(basket.count)
```

## Question 6

The below array represents an unfinished batting lineup for a baseball team. **You, the coach,** need to make some last minute changes:

- Add "Suzuki" to the end of your lineup.
- Change "Jeter" to "Tejada".
- Change "Thomas" for "Guerrero"
- Put "Reyes" to bat 8th instead.

`var battingLineup = ["Reyes", "Jeter", "Ramirez", "Pujols","Griffey","Thomas","Jones", "Rodriguez"]`

Answer:
```swift
var battingLineup = ["Reyes", "Jeter", "Ramirez", "Pujols","Griffey","Thomas","Jones", "Rodriguez"]
let newPlayer = "Suzuki"
var newSome = [String]()

//Add "Suzuki" to the end of your lineup.
battingLineup.append(newPlayer)

//Change "Jeter" to "Tejada".
for (index, player) in battingLineup.enumerated() {
if player == "Jeter" {
battingLineup[index] = "Tejada"
}
}

//Change "Thomas" for "Guerrero"
for (index, player) in battingLineup.enumerated() {
if player == "Thomas" {
battingLineup[index] = "Guerrero"
}
}

//Put "Reyes" to bat 8th instead.
for (index, player) in battingLineup.enumerated() {
if player == "Reyes" {
battingLineup.remove(at: index)
}
}
battingLineup.insert("Reyes", at: 7)

print(battingLineup)
```


## Question 7

Given an array of Ints, find out if it contains a target number.  

(The built-in `contains(_:)` function will do this, but you aren't allowed to use it for this exercise.)


```swift
var numbers: [Int]

let target: Int = 32
```

Ex.1

```swift
numbers = [4,2,6,73,32,4,2,1]

target = 32

//true
```

Ex. 2

```swift
numbers = [32459,2,4,5,1,4,2,1]

target = 3

//false
```

Answer:
```swift
var numbers: [Int]

let target: Int = 9

numbers = [4,2,6,73,32,4,2,1]

print(numbers.contains(target))
```

## Question 8

Find the largest value in an array of Int.  Do not use the built-in `max()` method.

```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

//This creates an array of 100 numbers in between 0 and 200.  For now, you don't need to worry about how it does that.
```
Answer:
```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}
var largestValue = 0

for number in arrayOfNumbers {
if number > largestValue {
largestValue = number
}
}

print(largestValue)
```

## Question 9

Find the smallest value in an array of Int.  Do not use the built in min() method.

```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

//This creates an array of 100 numbers in between 0 and 200.  For now, you don't need to worry about how it does that.
```
Answer:
```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}
var smallestValue = 200

for number in arrayOfNumbers {
if number < smallestValue {
smallestValue = number
}
}

print(smallestValue)
```

## Question 10

Iterate through `secondListOfNumbers`, and print out all the odd numbers.

`var secondListOfNumbers = [19,13,14,19,101,10000,141,404]`

Answer:
```swift
var secondListOfNumbers = [19,13,14,19,101,10000,141,404]
var oddNumbers = [Int]()

for number in secondListOfNumbers {
if number % 2 != 0 {    //odd
oddNumbers.append(number)
}
}
print(oddNumbers)
```

## Question 11

Iterate through `thirdListOfNumbers`, and print out the sum.

`var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]`

Answer:
```swift
var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]
var sum = 0

for number in thirdListOfNumbers {
sum += number
}
print(sum)
```

## Question 12

Iterate through `thirdListOfNumbers`, and print out the sum of all the even numbers.

`var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]`

Answer:
```swift
var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]
var sum = 0

for number in thirdListOfNumbers {
if number % 2 == 0 {
sum += number
}
}
print(sum)
```

## Question 13

Append every Int that appears in both `listOne` and `listTwo` to the `sharedElements` array. Then print **how many Ints** are shared.

```swift
var listOne = [28, 64, 7, 96, 13, 32, 94, 11, 80, 68]
var listTwo = [18, 94, 48, 6, 42, 68, 79, 76, 13, 7]
var sharedElements = [Int]()
```

Answer:
```swift
var listOne = [28, 64, 7, 96, 13, 32, 94, 11, 80, 68]
var listTwo = [18, 94, 48, 6, 42, 68, 79, 76, 13, 7]
var sharedElements = [Int]()

var commonElements = (listOne.filter(listTwo.contains))

for number in commonElements {
sharedElements.append(number)
}

print(sharedElements.count)
```


## Question 14

Write code such that `noDupeList` has all the same Ints as `dupeFriendlyList`, but has no more than one of each Int.

```swift
var dupeFriendlyList = [4,2,6,2,2,6,4,9,2,1]
var noDupeList: [Int] = []
```
Answer:
```swift
var dupeFriendlyList = [4,2,6,2,2,6,4,9,2,1]
var noDupeList: [Int] = []

for number in dupeFriendlyList {
if noDupeList.contains(number) {
continue
}
noDupeList.append(number)
}

print(noDupeList)
```

## Question 15

Find the second smallest number in an Array of Ints

`let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}`

Answer:
```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}
var smallestNumber = 10
var secondSmallest = 20

for number in arrayOfNumbers {
if number < smallestNumber {
smallestNumber = number
} else if number < secondSmallest && number > smallestNumber {
secondSmallest = number
}
}

print(secondSmallest)
```

## Question 16

If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Find the sum of all the multiples of 3 or 5 below 1000.

Answer:
```swift
let range = 0..<1000
var sum = 0

for number in range {
if number % 3 == 0 || number % 5 == 0 {
sum += number
}
}

print(sum)
```

## Question 17

Make an array that contains all elements that appear **more than twice** in `someRepeatsAgain`.

```swift
var someRepeatsAgain = [25,11,30,31,50,28,4,37,13,20,24,38,28,14,44,33,7,43,39,35,36,42,1,40,7,14,23,46,21,39,11,42,12,38,41,48,20,23,29,24,50,41,38,23,11,30,50,13,13,16,10,8,3,43,10,20,28,39,24,36,21,13,40,25,37,39,31,4,46,20,38,2,7,11,11,41,45,9,49,31,38,23,41,16,49,29,14,6,6,11,5,39,13,17,43,1,1,15,25]
```
```swift
var someRepeatsAgain = [25,11,30,31,50,28,4,37,13,20,24,38,28,14,44,33,7,43,39,35,36,42,1,40,7,14,23,46,21,39,11,42,12,38,41,48,20,23,29,24,50,41,38,23,11,30,50,13,13,16,10,8,3,43,10,20,28,39,24,36,21,13,40,25,37,39,31,4,46,20,38,2,7,11,11,41,45,9,49,31,38,23,41,16,49,29,14,6,6,11,5,39,13,17,43,1,1,15,25]
var newArray = Array(Set(someRepeatsAgain.filter({ (i: Int) in someRepeatsAgain.filter({ $0 == i }).count > 1})))

print(newArray)
```

## Question 18****

Identify if there are 3 integers that sum to 10 in the following array. If so, print them as a triplet. If there are multiple triplets, print all possible triplets.

`var tripleSumArr = [-20,-14, -8,-5,-3,-2,1,2,3,4,9,15,20,30]`

Answer: (Incomplete, I had trouble with this question)
```swift
//var tripleSumArr = [-20,-14, -8,-5,-3,-2,1,2,3,4,9,15,20,30]
//var sortedArr = tripleSumArr.sorted()
//
//for (index, number) in sortedArr.enumerated() {
//    if number.index + number.index+1 == 10 {
//
//    }
//}
```

## Question 19****

Given an array of Strings, find the the String with the most "a"s in it.

input: `["apes", "abba", "apple"]`

output: `"abba"`

Answer: (Incomplete, I had trouble with this question)
```swift
//let array = ["apes", "abba", "apple"]
//var mostAs:String = ""
//
//for word in array {
//    let howManyAs = word.components(separatedBy: "a")
//    if howManyAs.count > mostAs.count {
//        mostAs = word
//        mostAs.append(word)
//        }
//}
//print(mostAs)
```


## Question 20****

Given an Array of Arrays of Ints, find the Array of Ints with the largest sum:

Input: `[[2,4,1],[3,0],[9,3]]`

Output: `[9,3]`

Answer: (I had trouble with this one -- ended up with 2 outputs, one of which is the correct output)
```swift
let arraysOfArrays = [[2,4,1],[3,0],[9,3]]
var largestSumArray = [Int]()
var sum = 0

for array in arraysOfArrays {
let arraySum = array.reduce(0, +)
if arraySum > sum {
sum = arraySum
}
if arraySum == sum {
print(array)
}
}
```

## Question 21

Given an Array of Tuples of type `(Int, Int)`, create an array containing all the tuples where the first Int is equal to the second Int.

Input: `[(4,2), (-3,-3), (1,1), (3,9)]`

Output: `[(-3,-3), (1,1)]`

Answer:
```swift
let arrayOfTuples = [(4,2), (-3,-3), (1,1), (3,9)]

for tuple in arrayOfTuples {
if tuple.0 == tuple.1 {
print(tuple)
}
}
```


## Question 22

Given an Array of Bools, make a variable called `allAreTrue` that is true if all of the Bools are true and false if any of them are false.

Input: `[true, false, true, true]`

Output: `false`

Answer:
```swift
xlet arrayOfBools = [true, false, true, true]
var allAreTrue:Bool = false

if arrayOfBools.contains(false) {
allAreTrue = false
}
print(allAreTrue)
```


## Question 23

Given an Array of Ranges of Ints, create an array that has all the values from all the ranges in order from smallest to greatest with no duplicates.

Input: `[0..<3 , 2..<10, -4..<6, 13..<14]`

Output: `[-4,-3,-2,-1,0,1,2,3,4,5,6,7,8,9,10,13]`

Answer:
```swift
let arrayOfRanges = [0..<3 , 2..<10, -4..<6, 13..<14]
var newArray = [Int]()

for range in arrayOfRanges {
for number in range {
if newArray.contains(number) {
continue
}
newArray.append(number)
}
}
print(newArray.sorted())
```

## Question 24

Given an array of Characters, create a String ignoring uppercase Characters and spaces.  Then uppercase every other character of the String.

Input: `let arr: [Character] = ["a", "p","P","l","E"," ","S","a","u","C","e"]`

Output: `"ApLaUe"`

Answer:
```swift
let arr: [Character] = ["a", "p","P","l","E"," ","S","a","u","C","e"]
var newArr: [Character] = []
var finalArr: [String] = []

for character in arr {
if character.isUppercase == false && character != " " {
newArr.append(character)
}
}

for (index, character) in newArr.enumerated() {
if index % 2 == 0 {
finalArr.append(String(character.uppercased()))
} else {
finalArr.append(String(character))
}
}
print(finalArr)
```

## Question 25

Print out each element in `myMatrix`

`var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]`

Answer:
```swift
var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]

for array in myMatrix {
for element in array {
print(element)
}
}
```

## Question 26****

Print out the sum of the diagonals of `myMatrix`.

`var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]`

Answer: (Incomplete, I had trouble with this question)
```swift
var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]
var firstDiagnolSum = 0
var secondDiagnolSum = 0
var sum = 0

for (index, array) in myMatrix.enumerated() {
for (index, element) in array.enumerated() {
}
}
```

## Question 27****

Using for loops, rotate `matrixToRotate` 90 degrees.

var matrixToRotate = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

![Matrix Rotation](images/rotated_matrix.jpeg)

Answer: (I need help with this one!!)
