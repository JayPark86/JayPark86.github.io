# Typing Game

## Environment Setting

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

## Implementation for html
### Routing
1.


###



---
- Install webpack
- Install html and css loader/plugin for exporting
- Modify package.json
  - start script: add hot option
  - build script: make webpack.prod.js and use installed html and css loader/plugin to export to /public
- Install Mocha for unit testing


