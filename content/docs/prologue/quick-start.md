---
title: "Quick Start"
description: "One page summary of how to use JPigLatin"
lead: "One page summary of how to use JPigLatin"
date: 2020-11-16T13:59:39+01:00
lastmod: 2020-11-16T13:59:39+01:00
draft: false
images: []
menu: 
  docs:
    parent: "Prologue"
weight: 110
toc: true
---

## Installation

1) Via CDN  

*Replace version with current version, i.e `1.0.3`*

`<script src="https://unpkg.com/jpiglatin@VERSION/index.js"></script>`

1) Via NPM

`npm i jPigLatin -save`

## Use 

1) Include jPigLatin in page source  

`<script src="https://unpkg.com/jpiglatin@1.0.0/index.js"></script>`

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

## Code Pen Example

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="js,result" data-user="tcbutler320" data-slug-hash="JjRLeJm" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="JPigLatin | JavaScript Pig-Latin Encoder">
  <span>See the Pen <a href="https://codepen.io/tcbutler320/pen/JjRLeJm">
  JPigLatin | JavaScript Pig-Latin Encoder</a> by Tyler Butler (<a href="https://codepen.io/tcbutler320">@tcbutler320</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>