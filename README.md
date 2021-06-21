# CCS-Frontend-Kit

To use Frontend Kit:

1. Create a new project
	- mkdir [name of your project]
	- cd [name of your project]
	- npm init (to add package.json) file
	- npm install sass

2. Install Frontend Kit inside your project
	- npm install ccs-frontend-kit 
	- check node_modules to find ccs-frontend-kit package

3. Copy fonts, images and scripts to your project
	- at the root of your project’s folder, create an Assets folder and cd into it
	- copy and paste the following directories into your Assets folder:
		./node_modules/ccs-frontend-kit/Assets/fonts/
		./node_modules/ccs-frontend-kit/Assets/images/
		./node_modules/ccs-frontend-kit/Assets/scripts/ (can also add a script for this copy to package.json)
		copy the govuk package from inside the ./node_modules/govuk-frontend/ and paste it into your ./Assets/scripts/

4. Link the styles from ccs-frontend-kit to your project
	- create styles folder inside your Assets folder 
	- cd into your Assets/styles
	- create main scss file and inside your styles add the following line: 
	   @import "./node_modules/ccs-frontend-kit/Assets/styles/styles.scss/" (modify this path so that it correctly points to the imported file)
	- compile scss into css by running: sass main.scss main.css (can also add a script for this in package.json)
	- if there are errors during this compile, edit the import for govuk-frontend/govuk/all (inside the ./node_modules/ccs-frontend-kit/Assets/styles/styles.scss), so    that it points to the file correctly

5. Import the styles to your main html file
	- create an index.html file at the root of your project
	- add a link tag pointing to your compiled main.css 
		<link rel="stylesheet" href=“./Assets/styles/main.css">
	- add the following scripts at the bottom of the body tag inside the html file:
      - <script src=“./Assets/scripts/libraries/jquery-1.12.4.js"></script>
      - <script src=“./Assets/scripts/libraries/objectFitPolyfill.js"></script>
      - <script src=“./Assets/scripts/app.js"></script>
      - <script src=“./Assets/scripts/govuk/all.js"></script>
	- find and test a ccs html component by copying its markdown from gov website
