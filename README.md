# Hide the Chess.com rating and arrows
Hide the Chess.com rating and arrows so kids don't get distracted by them.

## 1- Add Tampermonkey extension to your browser

Add Tampermonkey 

[https://www.tampermonkey.net/](https://www.tampermonkey.net/)

 ⚠️ Tampermonkey note: Always review the code, verify the source, and avoid running unknown scripts. Stay safe! 🔒

## 2- Step for Chrome / Chrome-based browser users

For users of the Tampermonkey extension in a Chrome-based browser, enabling Developer Mode is a requirement.

Open the menu, select "Extensions" > "Manage extensions" and enable the "Developer Mode" using the toggle at the top.

[Click here for step-by-step illustrated instructions](https://www.tampermonkey.net/faq.php#Q209).

## 3- Create the script

Click on the extension button on your browser, then click on the tapermonkey extension > + Create a new script

## 4- Paste the script

Paste the following script on the Editor and save it using Ctrl+S or the Editor's menu: File > Save.

```javascript
// ==UserScript==
// @name Hide Chess.com rating and arrows
// @namespace http://tampermonkey.net/
// @version 1
// @description Hide the Chess.com rating and arrows so kids don't get distracted by them.
// @author alvaro
// @match *://*.chess.com/*
// @grant none
// ==/UserScript==

(function() {
    'use strict';

function removeElementsHTMLByClass(className) {

    if (document.getElementsByClassName(className)) {
        let els = document.getElementsByClassName(className);
        for (let i = 0; i < els.length; i++) {
            els[i].innerHTML = "";
        }
    }
}

setInterval(() => {

    // hide ratings
    removeElementsHTMLByClass("user-tagline-rating");
    removeElementsHTMLByClass("user-rating");
    removeElementsHTMLByClass("cc-user-rating-default");
    removeElementsHTMLByClass("cc-user-rating-white");
    removeElementsHTMLByClass("rating-score-rating");
    removeElementsHTMLByClass("rating-score-change rating-score-positive");
    removeElementsHTMLByClass("player-pieces");
    removeElementsHTMLByClass("resizable-chat-area-content");
    removeElementsHTMLByClass("game-over-message-component");
    removeElementsHTMLByClass("user-rating-rating");
    removeElementsHTMLByClass("rating-score-component");
    removeElementsHTMLByClass("user-tagline-rating user-tagline-white");
    removeElementsHTMLByClass("player-game-over-component");

    // hide arrows (remove the next line if you want the arrows):
    removeElementsHTMLByClass("arrows");

}, 5);

})();
```

## 5- Test

Go to chess.com and play.
