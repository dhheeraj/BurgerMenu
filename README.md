# BurgerMenu
This is SPFX burger menu navigation control, which extract navigation links from site collection term store.
Prerequiste
  1. install typings for sharepoints
  2. install react-render-html module
  3. Sharepoint site collection with publishing feature activated
      Term stores created for navigation
      3 level of heirarchy for navigation is supported.
 #Initial File changes
 1. tsConfig.json - replace with following values
  "types": [
      "es6-promise",
      "webpack-env",
      "microsoft-ajax",
      "sharepoint"
    ]
2. In Config>> Config.json
    under externals - replace with following values
    "sp-init": {
      "path": "./src/SP-JS/init.js",
      "globalName": "$_global_init"
    },
    "microsoft-ajax": {
      "path": "./src/SP-JS/MicrosoftAjax.js",
      "globalName": "Sys",
      "globalDependencies": [
        "sp-init"
      ]
    },
    "sp-runtime": {
      "path": "./src/SP-JS/SP.Runtime.js",
      "globalName": "SP",
      "globalDependencies": [
        "microsoft-ajax"
      ]
    },
    "sharepoint": {
      "path": "./src/SP-JS/SP.js",
      "globalName": "SP",
      "globalDependencies": [
        "sp-runtime"
      ]
    },
    "sp-taxonomy": {
      "path": "./src/SP-JS/sp-taxonomy.js",
      "globalName": "SP",
      "globalDependencies": [
        "sharepoint"
      ]
    }
