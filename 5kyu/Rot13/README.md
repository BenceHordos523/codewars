Description:
ROT13 is a simple letter substitution cipher that replaces a letter with the letter 13 letters after it in the alphabet. ROT13 is an example of the Caesar cipher.
Create a function that takes a string and returns the string ciphered with Rot13. If there are numbers or special characters included in the string, they should be returned as they are. Only letters from the latin/english alphabet should be shifted, like in the original Rot13 "implementation".

# My Solution

```
function rot13(message){
  let letters = message.split("")
  return letters.map(letter => {
    let charCode = letter.charCodeAt(0)
    if((charCode > 64 && charCode < 91) || (charCode > 96 && charCode < 123)) return codeShifting(letter.charCodeAt(0))
    else return letter
  }).join("")
}

function codeShifting(charCode){
   if(charCode > 96){
      if((charCode + 13) > 122){
        return String.fromCharCode(96 + ((charCode + 13) % 122))
      } else {
        return String.fromCharCode((charCode + 13))
      }
    } else {
      if((charCode + 13) > 90){
        return String.fromCharCode(64 + ((charCode + 13) % 90))
      } else {
        return String.fromCharCode((charCode + 13))
      }
    }
}
```

# Clever solution
```
const rot13 = str => str.replace(/[a-z]/gi, letter => String.fromCharCode(letter.charCodeAt(0) + (letter.toLowerCase() <= 'm' ? 13: -13)));
```
