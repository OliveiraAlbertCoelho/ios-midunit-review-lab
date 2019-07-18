## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

Input: `Hello, there`

Output: `HELLO, THERE`
```swift
var beforeString = "Hello, there"

var outputUppercase = beforeString.uppercased()

print(outputUppercase)
```

2. **Given a String, return a String alternating between uppercase and lowercase letters**


Input: `Hello, there`

Output: `HeLlO, tHeRe`
```swift
var beforeString = "Hello, there"
var afterString = ""
for (key,value) in beforeString.enumerated(){
if key % 2 == 0  {
afterString.append(value.uppercased())
}else {
afterString.append(value)
}

}
print(afterString)

```

3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`

Output: `Hllo, thr`
```swift
var beforeString = "Hello, there"
var skip = "e"
var anotherString = ""
for i in beforeString {

if i.lowercased() != skip.lowercased(){
anotherString.append(i)
}
}

print(anotherString)

```

## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`

Output: `5`
```swift
let reduceToFindLargestElement = clusterOfNums.reduce(0, {x, y in
return x > y ? x : y
//ternary operator -> condition ? true : false

})
print(reduceToFindLargestElement)
```
2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`

Output: `1`
```swift
let reduceToFindSmallestElement = clusterOfNums.reduce(0, {x, y in
return x < y ? x : y
//ternary operator -> condition ? true : false

})
print(reduceToFindSmallestElement)
```
3. **Given an array of type [Int], return its sum**

Input: `[1,5,2,4,1,4]`

Output: `17`
```swift
var someInput = [1,5,2,4,1,4]
let total = someInput.reduce(0, +)
print(total)

```
4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`

Output: `3.6`
```swift
var someInput = [3,4.5,7.5,2,1]
let total = someInput.reduce(0, +)
let average = total/Double(someInput.count)
print(average)

```
5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`

Output: `12`
```swift
var input = [3,4.5,7.5,2,1]
var sum:Double = 0
for i in input {
if i > 3 {
sum += i
}
}
print(sum)
```

6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`
```swift
var someInput = [3,4.5,7.5,2,1]
let total = someInput.reduce(1, *)
print(total)

```
7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`
```swift
var someInput = [20,10,1,3,4,0]
var small = Int.max
var secondSmall = 0
for i in someInput {
if i < small {
secondSmall = small
small = i
}
}
print(secondSmall)
```

## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`
Output: `["We", "come", "in", "peace"]`
```swift
var input = [nil, "We", "come", nil, "in", "peace"]
var secondArray = [String]()
for i in input {
if let check = i {
secondArray.append(check)
}
}
print(secondArray)


```
2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

Output: `[]`
```swift
var arrayOPt: [String?]?
var anotherArray = [String]()
if let checkA = arrayOPt {
for i in checkA{
if let checkB = i {
anotherArray.append(checkB)
}
}
}
print(anotherArray)

```
3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`

Output: `18`
```swift
var input = [4, nil, 9, 5, nil]
var sum = 0
for i in input {
if let check = i {
sum += check

}
}
print(sum)

```
4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`
```swift
var arrayOPt: [Int?]?
var sum = 0
if let checkA = arrayOPt {
for i in checkA{
if let checkB = i {
sum += checkB
}
}
}
print(sum)

```

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`
```swift
var optionalArray = [1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3]
var someNum: Int?
someNum = 1
var sum = 0
for i in optionalArray where i != nil{
if let checkA = i {
if someNum != checkA {
sum += checkA
}
}
}

print(sum)
```


## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`
```swift
var someDict = ["apple", "apple", "banana", "banana", "banana", "cake", "cake"]
var anoter = Set(someDict)
print(anoter)
```

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output: `t`
```swift
var Input = "Never trust a computer you can't throw out a window ~ Steve Wozniak"
var someDict = [Character:Int]()
var someLetter = "qwertyuiopasdfghjklzxcvbnm"
for i in Input where someLetter.contains(i) {

if someDict.keys.contains(i){
someDict.updateValue(someDict[i]!+1, forKey: i)
}
else {
someDict[i] = 1
}
}
print(someDict)
var mostFrequent = 0
var mostFrequenL = ""
for (k,v) in someDict {
if v > mostFrequent{
mostFrequent = v
mostFrequenL = String(k)
}
}
print(mostFrequenL)

```

3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**

Input: `[1,1,2,3,3,3,4,5,6,6,7]`

Output: `[1,3,6]`
```swift
var Input = [1,1,2,3,3,3,4,5,6,6,7]
var someDict = [Int:Int]()
for i in Input{
if someDict.keys.contains(i){
someDict.updateValue(someDict[i]!+1, forKey: i)
}
else {
someDict[i] = 1
}
}
print(someDict)

var daArray = [Int]()
for (k,v) in someDict {
if v >= 2 {
daArray.append(k)
}
}

print(daArray)
```

4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`
```swift
var Input = "Never trust a computer you can't throw out a window ~ Steve Wozniak"
var someDict = [Character:Int]()
var someLetter = "qwertyuiopasdfghjklzxcvbnm"
for i in Input where someLetter.contains(i) {

if someDict.keys.contains(i){
someDict.updateValue(someDict[i]!+1, forKey: i)
}
else {
someDict[i] = 1
}
}
print(someDict)
var mostFrequent = 0
var mostFrequenL = ""
var secondMost = 0
var secondMostL = ""
for (k,v) in someDict {
if v > mostFrequent{
secondMost = mostFrequent
secondMostL = mostFrequenL
mostFrequent = v
mostFrequenL = String(k)
}
}
print(secondMostL)

```

## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`
```swift
var daStrings = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

print(daStrings.sorted())
```
2. **Given an array of type [String], return an array that contains the Strings sorted by length**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`
```swift
print(thisArray.sorted(by: {$0.count < $1.count}))
```

3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`

4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`


## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

```swift
enum NumberType {
    case even
    case odd
}
```

Input: `[1,2,3,4,5,6], NumberType.odd`

Output: `[1,3,5]`

2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift
enum StringType {
    case lowercase
    case uppercase
}
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``

3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)
    var description: String {
        switch self {
        case .unsaved: return "Unsaved File"
        case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }
}
```

Input: `[FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)], 4`

Output: `[File that has been saved 5 times, File that has been saved 8 times]`
