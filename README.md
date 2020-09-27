# codewars-solutions
Solutions to www.codewars.com code challenges

# Go

## [Stop gninnipS My sdroW!](https://www.codewars.com/kata/5264d2b162488dc400000001) - 6kyu

```go
package kata
import ("strings")

func SpinWords(words string) string {
  wordArray := strings.Split(words, " ")
  for index, word  := range wordArray {
    if len(word) >= 5 {
      wordArray[index] = reverseString(word)
    }
  }
  return strings.Join(wordArray, " ")
}// SpinWords


func reverseString(str string) string {
  reversed := ""
  for _, char := range str {
     reversed = string(char) + reversed
    
  }
  return reversed
}
```


# TypeScript

## [Shortest Word](https://www.codewars.com/kata/57cebe1dc6fdc20c57000ac9) - 7kyu
```typescript
export function findShort(s: string): number {
  let length = 0
  s.split(" ").forEach((word, index) => {
    if(index == 0) length = word.length
    else if (word.length < length) length = word.length
  })
  return length
}
```

# Swift

## [Persistent Bugger](https://www.codewars.com/kata/55bf01e5a717a0d57e0000ec) - 6kyu
```swift
func persistence(for num: Int, count: Int = 0) -> Int {
  if num < 10 { return count }
  let numArray = Array(String(num))
  let newNum = numArray.reduce(1, { x, y in
    x * y.wholeNumberValue!
  })
  return persistence(for: newNum, count: count + 1) 
}
```

## [Good vs Evil]() - Xkyu
```swift
let goodArr = [
  1, // Hobbits
  2, // Men
  3, // Elves
  3, // Dwarves
  4, // Eagles
  10, // Wizards
]
let evilArr = [
  1, // Orcs
  2, // Men
  2, // Wargs
  2, // Goblins
  3, // Uruk Hai
  5, // Trolls
  10, // Wizards
]


func evaluate(good: String, vsEvil evil: String) -> String {
  // Convert string to number array "1 1 1 " -> [1, 1, 1]
  let totalGood = unitsToWorth(units: good.split(separator: " ").map { Int($0) ?? 0 }, worth: goodArr)
  let totalEvil = unitsToWorth(units: evil.split(separator: " ").map { Int($0) ?? 0 }, worth: evilArr)
  if totalGood > totalEvil { return "Battle Result: Good triumphs over Evil" }
  else if totalGood < totalEvil { return "Battle Result: Evil eradicates all trace of Good" }
  else { return "Battle Result: No victor on this battle field" }
}

// Convert array of units to total worth 
func unitsToWorth(units: [Int], worth: [Int]) -> Int {
  return units.enumerated().reduce(0) { (accumulate, current) in return accumulate + worth[current.0] * current.1}
```


# JavaScript

## [Moving Zeros To The End](https://www.codewars.com/kata/52597aa56021e91c93000cb0) - 5kyu
```javascript
var moveZeros = function (arr) {
  let zeros = []
  let index = arr.indexOf(0)
  while(index !== -1) {
    zeros.push(...arr.splice(index, 1))
    index = arr.indexOf(0)
  }
  return [...arr, ...zeros]
}
```

## [Breaking chocolate problem](https://www.codewars.com/kata/534ea96ebb17181947000ada) - 7kyu
```javascript
function breakChocolate(n,m) {
  return Math.max(0, (n*m) - 1);
}
```

## [Disemvowel Trolls](https://www.codewars.com/kata/52fba66badcd10859f00097e) - 7kyu
```javascript
function disemvowel(str) {
 const vowels = ['a', 'e', 'i', 'o', 'u']
 vowels.forEach(vowel => {
   str = str.split(new RegExp(vowel, "gi")).join('')
   })
 return str
}
```

## [Create Phone Number](https://www.codewars.com/kata/525f50e3b73515a6db000b83) - 6kyu
```javascript
function createPhoneNumber(numbers){
  return `(${numbers.slice(0,3).join('')}) ${numbers.slice(3,6).join('')}-${numbers.slice(6,10).join('')}`
}
```


# Template
## [Title](URL) - Xkyu
```language
```

