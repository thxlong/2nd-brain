## Step 1  -  Installing Bootstrap in Your Angular Project

-   Installing Bootstrap from npm using the `npm install` command


```bash
$ npm install bootstrap
```

-   Installing JQuery from npm using the `npm install` command
```bash
$ npm install jquery
```

## Step 2 
(Method 1)  -  Adding Bootstrap to Angular Using `angular.json`
Open the `angular.json` file of your project and include:

-   `node_modules/bootstrap/dist/css/bootstrap.css` in the `projects->architect->build->styles` array,
-   `node_modules/bootstrap/dist/js/bootstrap.js` in the `projects->architect->build->scripts` array,
-   `node_modules/bootstrap/dist/js/bootstrap.js` in the `projects->architect->build->scripts` array,

*As follows:*
```json
 "styles": [
 "./node_modules/bootstrap/dist/css/bootstrap.min.css",
 "./node_modules/@angular/material/prebuilt-themes/indigo-pink.css",
 "src/styles.scss"
 ],

 "scripts": [
 "./node_modules/jquery/dist/jquery.js",
 "./node_modules/bootstrap/dist/js/bootstrap.min.js"
 ]
```

(Method 2)  - Adding Bootstrap to Angular Using `index.html` or `CDN`

You can also include Bootstrap files from `node_modules/bootstrap` using the `index.html` file.

Open the `src/index.html` file and add the following tags:

-   A `<link>` tag for adding the `bootstrap.css` file in the `<head>` section,
-   A `<script>` tag for adding the `jquery.js` file before the closing `</body>` tag,
-   A `<script>` tag for adding the `bootstrap.js` file before the `</body>` tag.

*This is an example:*
```html
<!doctype html><html lang="en">
<head>  
<meta charset="utf-8">  
<title>Angular Bootstrap 4 Examples</title>  <base href="/">  
<meta name="viewport" content="width=device-width, initial-scale=1">  
<link rel="icon" type="image/x-icon" href="favicon.ico">  
<link rel="stylesheet" href="../node_modules/bootstrap/dist/css/bootstrap.css">
</head>
<body>  
<app-root></app-root>  
<script src="../node_modules/jquery/dist/jquery.js"></script>  <script src="../node_modules/bootstrap/dist/js/bootstrap.js"></script>    
</body>
</html>
```

(Method 3) - Adding Bootstrap to Angular Using `styles.css`

We can also use the `styles.css` file to add the CSS file of Bootstrap to our project.

Op*en the `src/styles.css` file of your Angular project and import the `bootstrap.css` file as follows:*
```css
@import "~bootstrap/dist/css/bootstrap.css"
```

## Referrence
[Import bootstrap to angular](https://www.techiediaries.com/angular-bootstrap/)