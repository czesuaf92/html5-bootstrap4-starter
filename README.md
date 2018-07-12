## Quick Start
```
# 1 Clone this repo
git clone https://github.com/wapbamboogie/bootstrap-4-boilerplate.git

# 2 Navigate into the repo directory
cd html5-bootstrap4-starter

# 3 Install all node packages
npm install

# 4 Get started

## starts localhost server with browser-sync, watches HTML, Sass, JS with hot reloading
gulp serve 
## minify CSS/JS and builds your app into the dist directory, ready for production
gulp
```

## Requirements
This project requires you have [nodejs](https://nodejs.org/en/) with [npm](https://www.npmjs.com/get-npm) installed.
This project requires you have a global installation of [gulp](http://gulpjs.com/).
```
# Install gulp globally
npm install -g gulp
```

## Gulp commands
**gulp serve**

The gulp serve command starts a local Browsersync server that serves your files in the browser.
It reloads the current page when changing HTML, PHP, Sass and JS files.
The output of all Sass files go to main.css
All JS files are concatenated into main.js
You can access the development server with other devices on the same network. Go to the "External" address specified by Browsersync (see the terminal) in the web browser of your device.
```
gulp serve
```

**gulp (build)**

The default gulp command is set to creating a "dist" directory with a production version of the project, ready to be deployed.
It minifies and renames JS/CSS assets as well as cleaning the old "dist" directory. CSS is autoprefixed for the latest two browser versions.
```
gulp
```

**gulp concatScripts**

The gulp concatScripts command combines the specified JS resources into main.js
You can add new JS files to this command on line 16 in gulpfile.js
You might want to run concatScripts once separately after adding new JS files.
```
gulp concatScripts
```

## Overwriting Bootstrap sass variables
You can overwrite specific bootstrap sass variables by uncommenting lines in assets/css/1-frameworks/bootstrap/bootstrap-user-variables.scss

## PHP
If you need a server with PHP support you can use the project with [MAMP Pro](https://www.mamp.info/en/mamp-pro/) or similar.
* Create a new host in the hosts panel of MAMP Pro and choose the project folder as the document root.
* Enable Symlinks settings in the "Extended" tab of the host configuration.
* On line 82 in gulpfile.js change the browserSync.init function to the following:
```
browserSync.init({
    proxy: "http://name-of-your-mamp-host:8888",
    open: "external"
});
```
* Start the MAMP services and run "gulp serve" as before.
