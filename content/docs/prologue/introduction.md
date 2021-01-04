---
title: "Introduction"
description: "JPigLatin is a translation and speech synthesis package"
lead: "JPigLatin is a translation and speech synthesis package"
date: 2020-10-06T08:48:57+00:00
lastmod: 2020-10-06T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "Prologue"
weight: 100
toc: true
---


[![Netlify Status](https://api.netlify.com/api/v1/badges/7cf029d4-056e-404d-a2e9-1fbdce6aaf26/deploy-status)](https://app.netlify.com/sites/sleepy-poitras-87fbed/deploys)  [![npm version](https://badge.fury.io/js/jpiglatin.svg)](https://badge.fury.io/js/jpiglatin)
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

## Contributing 
Feel free to make a pull request for features 
