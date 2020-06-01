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

### Game
1. Make unit tests for validation checking function
2. Make ajax.get and validation checking function for responseText  
  2-1. Parse responseText into JSON and send it to callback  
3. Make a loop which extracts words from data one by one  
  3-1. If words length is 0, calculate average time and navigate to end page  
  3-2. If not, set page with the extracted text, time and score  
4. Use setInterval to set game timer
5. Make setters which prints game text, time, and score on start page
6. Make setters which prints final score and average time on end page
7. Make onEnter and onUserInput event listener
8. Make start and end button event listener
