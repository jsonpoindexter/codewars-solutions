# [Duplicate Encoder](https://www.codewars.com/kata/54b42f9314d9229fd6000d9c) - 6 kyu
#### Completed: Thursday, November 5, 2020
### TypeScript
```typescript
export function duplicateEncode(word: string){
  let wordArr = word.toLowerCase().split('')
  const indexArr: number[][] = [] // Hold arr of char indexes. Example: din => [ [ 0 ], [ 1 ], [ 2 ] ]
  wordArr
    .filter((char, index) => wordArr.indexOf(char) === index) // Only itterate over unique chars
    .forEach((char, index) => { // Popoulate indexArr
      let currentIndex = 0;
      indexArr[index] = []
      while(wordArr.indexOf(char, currentIndex) > -1 && currentIndex < wordArr.length) {
        indexArr[index].push(wordArr.indexOf(char, currentIndex))
        currentIndex = wordArr.indexOf(char, currentIndex) + 1
      }
    })
  indexArr.forEach((wordIndexes) => wordIndexes.forEach(wordIndex => wordArr[wordIndex] = wordIndexes.length > 1 ? ')' : '('))
  return wordArr.join('')
}


```

# [Counting Duplicates](https://www.codewars.com/kata/54bf1c2cd5b56cc47f0007a1) - 6 kyu
#### Completed: Friday, November 6, 2020
### TypeScript
```typescript
export function duplicateCount(text: string): number{
  return text
    .toLowerCase()
    .split('')
    .reduce((accumulator, item, index, source) => {
            const nextItemIndex = source.indexOf(item, index + 1)
            const lastItemIndex = source.lastIndexOf(item)
            return accumulator + (index !== nextItemIndex && nextItemIndex === lastItemIndex ? 1 : 0)         
    }
  ,0)
}
```

# [Human Readable Time](https://www.codewars.com/kata/52685f7382004e774f0001f7) - 5 kyu
#### Completed: Thursday, November 5, 2020
### TypeScript
```typescript
export function humanReadable(seconds:number):string {
  const hours = Math.floor(seconds / (60 * 60))
  const minutes = Math.floor((seconds - (hours * 60 * 60)) / 60)
  seconds = Math.floor(seconds - (hours * 60 * 60) - (minutes * 60))
  return `${hours.toString().padStart(2, "0")}:${minutes.toString().padStart(2, "0")}:${seconds.toString().padStart(2, "0")}`
}
```

# [Are they the "same"?](https://www.codewars.com/kata/550498447451fbbd7600041c) - 6 kyu
#### Completed: Thursday, October 8, 2020
### Kotlin
```kotlin
fun comp(a: IntArray?, b: IntArray?): Boolean {
    if(a == null || b == null || !a.size.equals(b.size)) return false
    val bMut = b.toMutableList()
    a.forEach { aNum ->
        val index = bMut.indexOfFirst { it == aNum * aNum}
        if (index >= 0 ) bMut.removeAt(index)
        else return false
        
    }
    return bMut.size.equals(0)
}
```

# [Valid Braces](https://www.codewars.com/kata/5277c8a221e209d3f6000b56) - 6 kyu
#### Completed: Sunday, October 4, 2020
### TypeScript
```typescript
const OPEN_BRACES = '([{'
const CLOSE_BRACES = ')]}'

export function validBraces(braces: string): boolean {
  let currOpenBraces = '' // current open braces
  for(let brace of braces) {
    if (OPEN_BRACES.includes(brace)) currOpenBraces += brace // If open braces add to current open braces array
    else { // If close brace
      if(CLOSE_BRACES.indexOf(brace) === OPEN_BRACES.indexOf(currOpenBraces[currOpenBraces.length - 1])) { // and current close brace matches our last open brace
        currOpenBraces = currOpenBraces.substring(0, currOpenBraces.length - 1) // Pop off the last open braces
      }
      else return false // We have an invalid braces
    }
  }
  return !!currOpenBraces.length ? false : true
}
```

# [Valid Parentheses](https://www.codewars.com/kata/52774a314c2333f0a7000688) - 5 kyu
#### Completed: Wednesday, September 30, 2020
### JavaScript
```javascript
function validParentheses(parens) {
  try {
    return ![...parens].reduce((accumulator, item) => {
      if (!accumulator && item === ')') throw BreakException
      else return accumulator + (item === '(' ?  1 : -1)
    }, 0)
  } catch (_) {
     return false                     
  }
}
```

# [Help the bookseller !](https://www.codewars.com/kata/54dc6f5a224c26032800005c) - 6 kyu
#### Completed: Tuesday, September 29, 2020
### TypeScript
```typescript
export class G964 {
    public static stockList = (stockItems, categories) => {  
      if(stockItems.length === 0) return ""
      return categories.map((category) => {
        const amount = stockItems.filter((stockItem) => stockItem[0] === category).reduce((acc, curr) => {
          return acc + parseInt(curr.split(' ')[1])
        }, 0)
        return `(${category} : ${amount})`
      }).join(' - ')
    }
}
```

# [Stop gninnipS My sdroW!](https://www.codewars.com/kata/5264d2b162488dc400000001) - 6 kyu
#### Completed: Saturday, September 26, 2020
### Go
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

# [Moving Zeros To The End](https://www.codewars.com/kata/52597aa56021e91c93000cb0) - 5 kyu
#### Completed: Thursday, September 24, 2020
### JavaScript
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

# [Shortest Word](https://www.codewars.com/kata/57cebe1dc6fdc20c57000ac9) - 7 kyu
#### Completed: Wednesday, September 23, 2020
### TypeScript
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

# [Persistent Bugger.](https://www.codewars.com/kata/55bf01e5a717a0d57e0000ec) - 6 kyu
#### Completed: Wednesday, September 23, 2020
### Swift
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

# [Good vs Evil](https://www.codewars.com/kata/52761ee4cffbc69732000738) - 6 kyu
#### Completed: Wednesday, September 23, 2020
### Swift
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
}
```

# [Breaking chocolate problem](https://www.codewars.com/kata/534ea96ebb17181947000ada) - 7 kyu
#### Completed: Tuesday, September 22, 2020
### JavaScript
```javascript
function breakChocolate(n,m) {
  return Math.max(0, (n*m) - 1);
}
```

# [Disemvowel Trolls](https://www.codewars.com/kata/52fba66badcd10859f00097e) - 7 kyu
#### Completed: Tuesday, September 22, 2020
### JavaScript
```javascript
function disemvowel(str) {
 const vowels = ['a', 'e', 'i', 'o', 'u']
 vowels.forEach(vowel => {
   str = str.split(new RegExp(vowel, "gi")).join('')
   })
 return str
}
```

# [Create Phone Number](https://www.codewars.com/kata/525f50e3b73515a6db000b83) - 6 kyu
#### Completed: Tuesday, September 22, 2020
### JavaScript
```javascript
function createPhoneNumber(numbers){
  return `(${numbers.slice(0,3).join('')}) ${numbers.slice(3,6).join('')}-${numbers.slice(6,10).join('')}`
}
```

# [String ends with?](https://www.codewars.com/kata/51f2d1cafc9c0f745c00037d) - 7 kyu
#### Completed: Tuesday, September 22, 2020
### JavaScript
```javascript
function solution(str, ending){
  return ending === str.slice(str.length - ending.length, str.length)
}
```

# [Array.diff](https://www.codewars.com/kata/523f5d21c841566fde000009) - 6 kyu
#### Completed: Monday, September 21, 2020
### JavaScript
```javascript
function arrayDiff(arrayA, arrayB) {
  return arrayA.reduce((diff, currentItem) => {
     if(!arrayB.some(b => b === currentItem)) diff.push(currentItem) 
     return diff
  }, [])
}
```

# [Find the divisors! ](https://www.codewars.com/kata/544aed4c4a30184e960010f4) - 7 kyu
#### Completed: Wednesday, June 3, 2020
### Rust
```rust
fn divisors(integer: u32) -> Result<Vec<u32>, String> {
    let vec = (2..integer-1).filter(|x| integer % *x == 0).collect::<Vec<_>>();
    match vec.is_empty() {
        true => Err(String::from(integer.to_string() + " is prime")),
        false => Ok(vec),
    }
}
```

# [Find the odd int](https://www.codewars.com/kata/54da5a58ea159efa38000836) - 6 kyu
#### Completed: Friday, June 7, 2019
### JavaScript
```javascript
function findOdd(numArray) {
    return numArray.find((num) => {
        return numArray.filter(subNum => {
            return subNum === num
        }).length % 2
    })
}
```

# [Multiply](https://www.codewars.com/kata/50654ddff44f800200000004) - 8 kyu
#### Completed: Friday, May 31, 2019
### JavaScript
```javascript
function multiply(a, b){
  return a * b
}

```

