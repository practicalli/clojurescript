# Include Bootstrap

Lets make our website look better by adding some styling to the page.  Rather than spend days creating the perfect design, lets simply use Bootstrap.

> #### Note::Include Bootstrap CSS, Theme and Javascript to the project
> Edit the `resources/public/index.html` file and link the Bootstrap stylesheets and add the minified javascript.

<!--sec data-title="Reveal answer..." data-id="answer00" data-collapse=true ces-->

Bootstrap has been added to the `resources/public/index.html` page, in the header section.  To simplify things we have copied the CDN settings from [Getting Started with Bootstrap](http://getbootstrap.com/getting-started/).

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
<!-- Latest compiled and minified CSS -->
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">

<!-- Optional theme -->
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap-theme.min.css" integrity="sha384-rHyoN1iRsVXV4nD0JutlnGaslCJuC7uwjduW9SVrLvRYooPp2bWYgmgJQIXwl/Sp" crossorigin="anonymous">

<!-- Latest compiled and minified JavaScript -->
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>
    <link href="css/style.css" rel="stylesheet" type="text/css">
  </head>
  <body>
    <div id="app"></div>
    <script src="js/compiled/uswitch_conference_deux.js" type="text/javascript"></script>
  </body>
</html>
```

<!--endsec-->

> #### Hint::
> Adding Bootstrap from CDN is quicker than downloading it locally
>
> If you want to develop offline, then download the bootstrap CSS and Javascript files and place them in the `om-clojure/resources/public/` folder 
