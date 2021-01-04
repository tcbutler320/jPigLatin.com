---
title: "Advanced Use"
description: "Advnanced uses of JPigLatin"
lead: "Advnanced uses of JPigLatin"
date: 2020-11-16T13:59:39+01:00
lastmod: 2020-11-16T13:59:39+01:00
draft: false
images: []
menu: 
  docs:
    parent: "Prologue"
weight: 120
toc: true
---


## Getting User Input
Get user input using an html form. Make sure to set the `id` of `<textarea>` to `input`

```html
<form>
    <div class="form-group">
    <label for="exampleFormControlTextarea1"><h2 class="h4">Plain Text</h2></label>
    <textarea class="form-control" id="input" rows="3"  placeholder="I love pig latin ..."></textarea>
    </div>
</form>
```

## Pig-Latin to Speech  
Use the following javaScript function to read the converted pig-latin output

```javascript
function talkToMe() {
    if ('speechSynthesis' in window) {
        var msg = new SpeechSynthesisUtterance();
        msg.text = document.getElementById("output").innerHTML;
        window.speechSynthesis.speak(msg);
    }else{
        alert("Sorry, your browser doesn't support text to speech!");
    }

}
```

## Error Handling 
The  `encode()` function throws an error when plaintext input is undefined. This typically happens when the end of user input has a space.

```javascript
typeof temp === 'undefined' || typeof words[i][0] === 'undefined'
```

Wrapping a call to the `encode()` function in a try/catch allows you to display a message to the user.

```javascript
function displayPigLatin(){
    var input = "input";
    var output = "output";
    var error = "error";
        try {
            document.getElementById(output).innerHTML = encode(input,output);
            document.getElementById(error).innerHTML = "";
        } catch(err) {
            document.getElementById(error).innerHTML = "Enter a plain text string with no spaces at the end!";
        }
}
```  

Set a display tag to `error` to show the message using the `onclick()` for your translate button. 

```html
<p id="error" style="color:red"></p>
```