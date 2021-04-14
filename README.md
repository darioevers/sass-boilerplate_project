# HOW TO CREATE A SASS ENVIRONMENT

1. Use command "NPM INIT" in the directory you want to work in
2. Use command "npm i --save-dev gh-pages sass live-server npm-run-all" in the same directory to install needed items
3. delete test scripts in package.json file
4. add to scripts (package.json file) in curly brackets:
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
5. create .gitignore in root/main folder and add node_modules to .gitignore
6. add folder to root/main folder: "src"
7. add "index.html" to "src" folder
8. add folder "scss" to folder "src"
9. add "main.scss" to "scss" folder
10. run "npm start" and "styles" folder gets automatically created with main.css and main.css.map
11. link "main.css" from newly created folder to index.html doc
12. Dont use this terminal window anymore, except:
    12.1 Everytime you change files or directorynames, installing and updating packages, you need to restart the liveserver
13. Everytime you make changes and save in main.scss, its content gets transferred to main.css
14. "npm run build" in another terminal-window in the same directory to create gh-pages version or update gh-pages version in /dist folder
