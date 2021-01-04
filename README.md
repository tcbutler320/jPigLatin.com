# JPigLatin.com
> landing page for jPigLatin, the Javascript Pig-Latin Generator 🐷 


[![Netlify Status](https://api.netlify.com/api/v1/badges/7cf029d4-056e-404d-a2e9-1fbdce6aaf26/deploy-status)](https://app.netlify.com/sites/sleepy-poitras-87fbed/deploys)  [![npm version](https://badge.fury.io/js/jpiglatin.svg)](https://badge.fury.io/js/jpiglatin)

JPigLatin.com is the landing page for the jPigLatin npm package. JPigLatin is a javascript package that takes plain text and converts it into pig-latin. The site is built with Netlify and the Doks Hugo Theme.

![](jPigLatin.gif)  


## About  
JPigLatin is a javascript package that takes plain text and converts it into pig-latin. Originally inspired by an episode of [Stuff You Should Know](https://open.spotify.com/episode/1Lvn2Wuck6kC6x1cQu68fE?si=TR84xSzYQAqZPfEdj68Dsw), the project was created to learn more about developing packages on NPM.

## How it works  
The actual code is pretty simple. The main function `encode` accepts the ElementID's of user-supplied input , proccesses it with simple pig-latin based rules, and returns the encoded output. Developers can set the output of `encode` using innerHTML to display the output. See [quick start](/docs/Prologue/quick-start/) to see an example.

```javascript
function encode(input,output) {
  var string = document.getElementById(input).value;
  var words = string.split(" ");
  var answer = "";
  var temp = "";
  for (var i = 0; i < words.length; i += 1) {
      temp = words[i].slice(1);
        if (typeof temp === 'undefined' || typeof words[i][0] === 'undefined') {
          break;
        } else {
          answer = answer + (temp.toLowerCase()+words[i][0].toLowerCase()+"ay") + " ";
        }
   }
    return answer;
 }
```
## Quick Start 

### Installation

1) Via CDN  

*Replace version with current version, i.e `1.0.3`*

`<script src="https://unpkg.com/jpiglatin@VERSION/index.js"></script>`

1) Via NPM

`npm i jPigLatin -save`

### Use 

1) Include jPigLatin in page source  

`<script src="https://unpkg.com/jpiglatin@1.0.2/index.js"></script>`

2) Create two fields, one for user input and one for output
   
```html
<span id="input">This is a test</span>
<span id="output"></span>
```

3) Use javascript to get pass input to jPigLatin `encode()` function. Set input and output ElementID's with local variables.

```javascript
<script>
    function displayPigLatin(){
        var input = "input";
        var output = "output";
        document.getElementById(output).innerHTML = encode(input,output);
    }
</script>
```

4) Use an event loader to execute function

```html
<button onclick="displayPigLatin()">Translate</button>
```  

## Contributing 
Feel free to make a pull request for features 
## Thanks 🙏  
Special thanks to those below who were inspirations for this quick project  

1) Henk Verlinde whoose open source Jekyll theme `doks` was the base template for the applicaiton. Check out more of his awesome work on his [GitHub page](https://github.com/h-enk) and see the original theme for yourself [here](https://github.com/h-enk/doks)

2) Asaolu Elijah 🧙‍♂️ for his article "Text To Speech In 3 Lines Of JavaScript" on Dev.To, read the full article [here](https://dev.to/asaoluelijah/text-to-speech-in-3-lines-of-javascript-b8h)

3) [Josh Clark](https://twitter.com/josh_um_clark?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) and [Chuck Bryant](https://www.instagram.com/chuckthepodcaster/?hl=en) for the great podcasts and inspiration
