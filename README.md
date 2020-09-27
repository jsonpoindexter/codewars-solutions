# codewars-solutions
Solutions to www.codewars.com code challenges

# JavaScript
## Moving Zeros To The End
https://www.codewars.com/kata/52597aa56021e91c93000cb0
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

# Go
## Stop gninnipS My sdroW!
https://www.codewars.com/kata/5264d2b162488dc400000001

> Write a function that takes in a string of one or more words, and returns the same string, but with all five or more letter words reversed (Just like the name of this Kata). Strings passed in will consist of only letters and spaces. Spaces will be included only when more than one word is present.

> Examples: spinWords( "Hey fellow warriors" ) => returns "Hey wollef sroirraw" spinWords( "This is a test") => returns "This is a test" spinWords( "This is another test" )=> returns "This is rehtona test"

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

