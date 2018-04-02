# node-bashdeck
This is a simple node.js app to send bash commands and customized icon buttons to an Elgato Stream Deck on Linux.

![All Buttons](/examples/default-config.jpg "Default Command Layout")

I was looking for a way to use the Stream Deck with linux I don't really do any streaming or PC gaming but I thought it was an interesting input device. I found [node-oscdeck](https://github.com/loveolsson/node-oscdeck) which used the [Google Material Design](https://materialdesignicons.com/) icon set svg files and allowed for text to be added to the buttons.

I wanted to be able to run arbitrary commands from buttons I replaced the lines sending OSC commands with a bash command and renamed the functions and elements in the JSON files to reflect the change to sending commands.

## Buttons
Each file in the configs folder contains a "buttons" array of objects describing each button on the Stream Deck. Below is an example for button 0 (top right).  By default the default.json file is loaded which contains all 5 buttons and writes text to the console log.

```
  {
    "key": 0,                   // The key to assign to, check node-elgato-stream-deck button map
    "symbol": "skip-forward",   // The icon rendered on the button,
                                // referring to the names from https://materialdesignicons.com/
    "color": "green",           // Color of symbol; "red", "#FF0000", "rgb(255, 0, 0)"
    "text": "SKIP",             // Text rendered on button. If left blank, the icon is rendered bigger.
    "cmdDown": [0, "/skip", 1], // The cmd message to send when button is pressed. [cmd, value]
    "cmdUp": [0, "/skip", 0]    // The cmd message to send when button is released. [cmd, value]
  }
```

![Desktop Layout](/examples/solus-config.jpg "Solus Desktop Command Layout")

I was able to set up all of the progams and webpages I wanted the stream deck to open for me on my solus gnome desktop using bash commands.  There are thousands of material design icons and the parse-color plugin does a great job loading named css colors.

After getting the stream deck to work as a fancy lancher for my solus desktop I made a couple of other button layouts.

![Sentiment Layout](/examples/sentiment-config.jpg "Sentiment Command Layout")

![Star Rating Layout](/examples/star-rating-config.jpg "Star Rating Command Layout")

## Dependancies
```
  npm install
    elgato-stream-deck
    material-design-icons-svg
    parse-color
    lodash
    sharp
```




