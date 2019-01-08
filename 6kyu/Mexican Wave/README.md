In this simple Kata your task is to create a function that turns a string into a Mexican Wave. You will be passed a string and you must return that string in an array where an uppercase letter is a person standing up.

# Example
```
wave("hello") => ["Hello", "hEllo", "heLlo", "helLo", "hellO"]
```

# My Solution
```
function wave(text){
  if(text.length === 0){
    return []
  } else {
    let waveArray = []
    for(let i = 0; i<text.length; i++){
      if(text[i] !== " ") {
        waveArray.push(text.substr(0,i) + text[i].toUpperCase() + text.substr(i + 1,text.length))
      }
    }
    return waveArray;
  }
}
```

# Other Solution
```
function wave(str){
    let result = [];
    
    str.split("").forEach((char, index) => {
        if (/[a-z]/.test(char)) {
            result.push(str.slice(0, index) + char.toUpperCase() + str.slice(index + 1));
        }
    });
    
    return result;
}
```
