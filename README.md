# firefox-extension-base

The web is a magical place full of possibilities. I like building web applications because the web connects people and enables interaction between them. With extensions you can create interactions of your own. Extensions, however, are not like regular web apps. They require a different way of working that is new to me. The goal of this repository is to make it easy for anyone to make a (firefox) extension.

## Example 1: a red border around mozilla.org (or any other website)

This example comes straight from mozilla: https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Your_first_WebExtension. It helps you write an extension that, when loaded into your browser as an add-on, adds a red border to the body of mozilla.org. The `manifest.json` file contains the most important part that makes it all work:

```json
"content_scripts": [
    {
      "matches": ["*://*.mozilla.org/*"],
      "js": ["borderify.js"]
    }
  ]
```

This part of the extension manifest registers a hook in your browser to execute a script when a certain url is loaded. The script has access to the document object of the page (among other things) that is loaded via the url.
