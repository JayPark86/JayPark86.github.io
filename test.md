# Typing Game

## Environment Setting
- Install webpack
- Install html and css loader/plugin for exporting
- Modify package.json
  - start script: add hot option
  - build script: make webpack.prod.js and use installed html and css loader/plugin to export to /public
- Install Mocha for unit testing

### webpack and plugin installation
**webpack**
```
npm install --save-dev webpack webpack-dev-server
```
**html, css plugin**
```
npm install --save-dev html-loader html-webpack-plugin
npm install --save-dev css-loader mini-css-extract-plugin
```

### package.json
**start/build script**
```
"scripts": {
    "start": "webpack-dev-server --hot --progress --config webpack.dev.js",
    "build": "webpack --config webpack.prod.js"
}
```
**unit test**
```
```

### webpack.dev.js
- set devServer for webpack-dev-server

### webpack.prod.js
- set entry, output, module rules, plugins

---
## Implementation for fn
### Get words from server and parse JSON
1. Make validate fn to verify 'time' and 'text'
```
**Make unit test**
  - Case 'time' is Number and greater than 0
  - Case 'text' length is greater than 0
- Make validate fn 
```

2. Make validate fn to verify JSON response
```
- Make unit test
  - Case failed/timeout : Alert msg
  - Case 0 length : Alert msg
  - Case greater than 1
- Make validate fn
```

3. Make ajax request and parse response(JSON)
```
- Make request fn and verify using unit tests above
```

### Fn for game
1. Make timer and score fn for the game
```
- Make unit test for timer
  - Check whether the timer prints decreasing number every seconds
- Make timer fn
- Make unit test for score
  - Check if the first score is the number of the game texts
  - Check if the score decreases by 1 on timeout or incorrect input text
- Make score fn
```

## Implementation for html
### Routing
1.


###

