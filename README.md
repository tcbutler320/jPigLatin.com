# JPigLatin a Javascript Pig-Latin Generator 🐷   

[![Netlify Status](https://api.netlify.com/api/v1/badges/7cf029d4-056e-404d-a2e9-1fbdce6aaf26/deploy-status)](https://app.netlify.com/sites/sleepy-poitras-87fbed/deploys)  

A simple javascript web application that translates plaintext into Pig Latin. Built with Netlify and the Doks Hugo Theme. Inspired by the Stuff You Should Know ([SYSK](https://open.spotify.com/episode/1Lvn2Wuck6kC6x1cQu68fE?si=MZlDRPCtQgOlhUKqrkr3VA)) podcast
# How Does it Work ? 


## Plain Text to Pig-Latin
The actual translation is a few simple lines of javascript ...

```javascript
function myFunction() {
var string = document.getElementById("input").value;
var words = string.split(" ");
var answer = "";
var temp = "";
for (var i = 0; i < words.length; i += 1) {
    temp = words[i].slice(1);
    if(typeof temp === 'undefined' || typeof words[i][0] === 'undefined') {
        document.getElementById("out").innerHTML = "<span style='color: red;'> Don't use puncuation or spaces at the end </span>";
        break;
    } else {
        answer = answer + (temp.toLowerCase()+words[i][0].toLowerCase()+"ay") + " ";
    }
    document.getElementById("out").innerHTML = answer;
}
}
```
## Speech Synthesis
Speech synthesis is another few lines of javascript curtosy of a dev.to article from [Asaolu Elijah 🧙‍♂️](https://dev.to/asaoluelijah/text-to-speech-in-3-lines-of-javascript-b8h)  

```javascript
function talkToMe() {
    if ('speechSynthesis' in window) {
    // Speech Synthesis supported 🎉
    var msg = new SpeechSynthesisUtterance();
    msg.text = document.getElementById("out").innerHTML;
    window.speechSynthesis.speak(msg);
    }else{
        // Speech Synthesis Not Supported 😣
        alert("Sorry, your browser doesn't support text to speech!");
    }
}
```

# Contributing ✍️
Feel free to make pull requests for new features

# Thanks 🙏  
Special thanks to those below who were inspirations for this quick project  

1) Henk Verlinde whoose open source Jekyll theme `doks` was the base template for the applicaiton. Check out more of his awesome work on his [GitHub page](https://github.com/h-enk) and see the original theme for yourself [here](https://github.com/h-enk/doks)

2) Asaolu Elijah 🧙‍♂️ for his article "Text To Speech In 3 Lines Of JavaScript" on Dev.To, read the full article [here](https://dev.to/asaoluelijah/text-to-speech-in-3-lines-of-javascript-b8h)

3) [Josh Clark](https://twitter.com/josh_um_clark?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) and [Chuck Bryant](https://www.instagram.com/chuckthepodcaster/?hl=en) for the great podcasts and inspiration
