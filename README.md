# electron-clipboard-watcher2
This is a modified version of electron-clipboard-watcher,
this modification includes the exclution of image text data being polled by the watcher

Poll the system clipboard for changing text or image data.

##
Differences between 1 and 2: 

`--  onTextChange callback now returns an object with 2 properties`

```
{
  isImage: [bool], // Is the copied content image data
  text: [string] // Copied content
}
```




## Install

`npm install --save electron-clipboard-watcher2`

## Usage

Start polling the clipboard for changes.

Usage:

```
const clipboardWatcher = require('electron-clipboard-watcher')
clipboardWatcher({
  // (optional) delay in ms between polls
  watchDelay: 1000,

  // handler for when image data is copied into the clipboard
  onImageChange: function (nativeImage) { ... },

  // handler for when text data is copied into the clipboard
  onTextChange: function (text) { ... }
})
```

The `clipboardWatcher` function returns an object with a `stop()`
function which you can use to deactivate the polling:

```
const watcher = clipboardWatcher({ ... })
watcher.stop()
```

## License

MIT
