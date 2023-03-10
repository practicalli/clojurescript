# Create a web page

Create a file `index.html` and include the following:

```html
<html>
    <body>
        <script type="text/javascript" src="out/main.js"></script>
    </body>
</html>
```

Open this file in a browser and open the JavaScript developer console so you can see the output. Nothing will
appear in the main browser window as no content is rendered.

You will not see `"Hello world!"` but instead you will likely see an error like the following:

```
Uncaught ReferenceError: goog is not defined
```

In order to understand this error we must examine a few basics around the Google Closure Library. While the following section may seem somewhat roundabout, a short review on how Google Closure Library works will make simple bugs considerably easier to spot.
