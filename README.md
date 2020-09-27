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

## Good vs Evil

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
