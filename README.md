1. NPM INIT 2.
2. npm i gh-pages sass live-server npm-run-all
3. delete test scripts
4. add to scripts in curly brackets:
   "start": "run-p watch watch:styles",
   "build": "run-s clean clean:styles build:styles copy",
   "deploy": "run-s build publish",
   "build:styles": "sass src/scss:src/styles",
   "watch": "live-server src",
   "watch:styles": "sass src/scss:src/styles --watch",
   "clean": "rm -rf dist",
   "clean:styles": "rm -rf src/styles",
   "copy": "mkdir dist && rsync -avr --exclude=\"/scss\" src/ dist",
   "publish": "gh-pages -d dist"
5. create .gitignore in root/main folder and add node modules to .gitignore
6. add folder to root/main folder: "src"
7. add "index.html" to "src"
8. add folder "scss" to folder "src"
9. add "main.scss" to "scss" folder
10. "styles" folder gets automatically created with main.css and main.css.map
11. link "main.css" from newly created folder to index.html doc
12. type "npm run" in terminal to start the liveserver and dont use this terminal window anymore
13. Everytime you change files or directorynames, installing and updating packages, you need to restart the liveserver
14. Everytime you make changes and save in main.scss, its content gets transferred to main.css
15. "npm run build" in terminal to create gh-pages version or update gh-pages version in /dist folder
