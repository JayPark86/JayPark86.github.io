# Typing Game

## Environment Setting
- OS : Ubuntu Linux System
- Development tool : vim

### webpack and plugin installation
**webpack**
```
npm install --save-dev webpack webpack-dev-server webpack-cli
```
**html, css plugin**
```
npm install --save-dev html-loader html-webpack-plugin
npm install --save-dev css-loader mini-css-extract-plugin
```
**babel for ES6**
```
npm install --save-dev babel-loader @babel/core
```
**mocha unit test**
```
npm install --save-dev mocha
```  

### package.json
**start/build script & unit test script**
```
"scripts": {
    "test": "./node_modules/mocha/bin/mocha $(find ./src/ -name '*.test.js') --recursive -w"
    "start": "webpack-dev-server --hot --progress --config webpack.dev.js",
    "build": "webpack --config webpack.prod.js"
}
```

### webpack.dev.js
- set devServer for webpack-dev-server

### webpack.prod.js
- set entry, output, module rules, plugins

---
## Implementation Strategy
### HTML
1. Make main div index page

### Routing
1. Make templates for start and end page
2. Make routes[] and router to set template pages with path

### Utils
1. Make validation checking function for the responseText
2. Parse responseText into JSON and send it to callback

### Game
1. Send and receive parsed JSON data by callback
2. The callback will check validation of the data by using Utils
3. Make a loop which extracts words from data one by one
3-1. If words length is 0, calculate average time and navigate to end page
3-2. If not, set page with the extracted text, time and score
4. Use setInterval to set timer

---
---

### Routing
1. Make index.html for main div tag
2. Make template for game start page and end page
3. Make routes array to store page with path
4. Make router function which push current path to window.history and load page template from routes

### utils
#### ajax.get
1. Make ajax.get function which request and get responseText using url from parameter
2. Parse the responseText to JSON and send it to callback function
#### avg
1. Make unit test
2-1. Make the utility function which returns average value using dividend and divider from parameter
2-2. Returns 0 if either the dividend or divider is 0.
#### isTextValid
1. Make unit test
2. Make a function returns true if the length of the param is greater than 0
#### isTimeValid
1. Make unit test
2. Make a function returns true if the param is not NAN and greater than 0
#### isWordValid
1. Make a function returns true if isTextValid() and isTimeValid() is true
#### extractValidWords
1. Make unit test
2. Make a function which excludes invalid words using isWordValid()

### game function
#### setters
1. Make setters which prints game text, time, and score on start page
2. Make setters which prints final score and average taken time on end page
3. 

#### start page
1. Make onStart() which get game words from ajax.get by sending url and startGame() as a callback
2. Make startGame() 
2. Make onReset() 

#### 

#### end page 

#### event listener






---
### unit test
### Get words from server and parse JSON
1. Make validate fn to verify 'time' and 'text'
```
1.) Make unit test
  - success: 'time' is Number and greater than 0
  - fail: 'time' is not Number or less than 1
  - success: 'text' length is greater than 0
  - fail: 'text' length is 0
2.) Make fn 
```

2. Make validate fn to verify JSON response
```
1.) Make unit test
  - fail: timeout(set to 5 seconds)
  - fail: if length is 0
  - success: if length is greater than 1
2.) Make fn
```

3. Make ajax request and parse response(JSON)
```
1.) Make request fn and verify using unit tests above
```

### Fn for game
1. Make timer and score fn for the game
```
1.) Make unit test for timer
  - Check whether the timer prints decreasing number every seconds
2.) Make timer fn
3.) Make unit test for score
  - Check if the first score is the number of the game texts
  - Check if the score decreases by 1 on timeout or incorrect input text
4.) Make score fn
```
