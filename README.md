# CCS-Frontend-Kit
Npm package that contains all the styles and assets of the CCS website. 
This is so that any new projects can import the same css and keep the styles consistent across all applications in CCS.

&nbsp;

  
### Create a new project
```
$ mkdir [name of your project]
$ cd [name of your project]
$ npm init
$ npm install sass
```
&nbsp;

### Install Frontend Kit inside your project
```
$ npm install ccs-frontend-kit 
```
```
check `node_modules` to find ccs-frontend-kit package
```
&nbsp;


### Copy fonts, images and scripts to your project

At the root of your project:
```
$ mkdir Assets && cd Assets
```
&nbsp;


### Copy fonts, images and scripts into your Assets folder:
```
$ cp ./node_modules/ccs-frontend-kit/Assets/fonts ./Assets
$ cp ./node_modules/ccs-frontend-kit/Assets/images/ ./Assets
$ cp ./node_modules/ccs-frontend-kit/Assets/scripts/ ./Assets
```
(You can also add a script for this copy to package.json)

&nbsp;


### Copy the govuk package 
```
$ cp ./node_modules/govuk-frontend/govuk ./Assets/scripts
```
&nbsp;


### Link the styles from ccs-frontend-kit to your project
```
$ cd Assets && mkdir styles
$ cd styles
$ touch main.scss
```
Add the following line inside main.scss:
```
@import "./../../node_modules/ccs-frontend-kit/Assets/styles/styles.scss/"
```
If needed, modify this path so that it correctly points to the imported file.

Compile scss into css :
```
$ sass main.scss main.css 
```
(You can also add a script for this in package.json)

If there are errors during this compile, edit the import for `govuk-frontend/govuk/all` from inside the `./node_modules/ccs-frontend-kit/Assets/styles/styles.scss`, so that it points to the file correctly.

&nbsp;


### Import the styles to your main html file
At the root of your project
```
$ touch index.html
```

Inside the `<head>` tag, add a link tag pointing to your compiled main.css:
```
<link rel="stylesheet" href=“./Assets/styles/main.css">
```

Add these scripts at the bottom of the `<body>` tag:
```
<body>
  ...
  <script src=“./Assets/scripts/libraries/jquery-1.12.4.js"></script>
  <script src=“./Assets/scripts/libraries/objectFitPolyfill.js"></script>
  <script src=“./Assets/scripts/app.js"></script>
  <script src=“./Assets/scripts/govuk/all.js"></script>
</body>
```
Find and test a component by copying its markdown from https://gov.uk website.
