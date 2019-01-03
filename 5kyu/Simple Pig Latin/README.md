Description:
Move the first letter of each word to the end of it, then add "ay" to the end of the word. Leave punctuation marks untouched.

# Examples

```
pigIt('Pig latin is cool'); // igPay atinlay siay oolcay
pigIt('Hello world !');     // elloHay orldway !
```

# My Solution

```
function pigIt(str){
  let words = str.split(" ")
  return words.map(word => {
      let regex = /^[A-Za-z]+$/
      if(regex.test(word)){
        return word.substr(1,word.length) + word[0] + 'ay'
      } else {
        return word
      }
    }).join(" ")
}
```

# Best solution

```
function pigIt(str){
  return str.replace(/(\w)(\w*)(\s|$)/g, "\$2\$1ay\$3")
}
```

