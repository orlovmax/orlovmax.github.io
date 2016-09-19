# Synteagle general project template

General template for common web development tasks based on [front-end-scaffold](https://github.com/orlovmax/front-end-scaffold), with common used technologies and tools.

## Contents
* [Folder structure](#folder-and-file-structure)
* [Requirements](#requirements)
	- [Editorconfig](#editorconfig)
* [How to start](#how-to-start)
* [Site configuration](#site-configuration)
* [Tasks](#tasks)
	- [Start](#start)
	- [Dev](#dev)
	- [Build](#build)
	- [Rebuild](#rebuild)
	- [Server](#server)
	- [Sprite](#sprite)
* [Live reload](#live-reload)
* [License](#license)

## Folder and file structure
```
./
├── .editorconfig
├── bower.json
├── README.md
├── automation.sh
|
├── _automation/                               * build systems
|	├── _grunt/                                * grunt build system
|	|	├── grunt_tasks/                       * grunt tasks
|	|	|   ├── config/                        * grunt tasks config
|	|	│   |	├── paths.js
|	|	│   |	├── settings.js
|	|	│   |	└── aliases.js
|	|	│   |
|	|	|   └── task.js
|	|	│
|	|	├── Gruntfile.js
|	|	└── package.json
|	|
|	└── _gulp/                                 * gulp build system
|		├── gulp_tasks/                        * gulp tasks
|		|   ├── config/                        * gulp tasks config
|		│   |	├── paths.js
|		│   |	├── settings.js
|		│   |	└── aliases.js
|		│   |
|		|   └── task.js
|		│
|		├── gulpfile.js
|		└── package.json
|
├── screenshots/                               * responsive test screenshots
|
├── dev/                                       * site source
|   ├── coffee/                                * coffee scripts
|	│
│   ├── images/                                * image sources
|	│
│   ├── pug/                                   * templates
|	|	├── blocks/                            * blocks library
|	│   |   └── block.pug
|	│   ├── helpers/                           * helper mixins
|	│   ├── vendor/                            * third-party code
|	│   ├── layouts/                           * page layouts
|	│   └── pages/                             * main pages templates
|	│
│   ├── js/                                    * compiled and source js
|	|   ├── vendor/                            * vendor scripts library
|	|   ├── lib/                               * site scripts library
|	│   ├── head.js                            * head scripts
|	│   └── body.js                            * vendor scripts
|	│
|	├── sass/                                  * sass preprocessor styles
|	|	├── blocks/                            * blocks library
|	│   |   └── block.sass
|	│   ├── helpers/                           * mixins and vars
|	│   ├── vendor/                            * third-party code
|	│   ├── custom.sass
|	│   ├── noscript.sass
|	│   └── screen.sass
|	│
|	├── stylus/                                * stylus preprocessor styles
|	|	├── blocks/                            * blocks library
|	│   |   └── block.styl
|	│   ├── helpers/                           * mixins and vars
|	│   ├── vendor/                            * third-party code
|	│   ├── custom.styl
|	│   ├── noscript.styl
|	│   └── screen.styl
|	│
│   ├── helpers/                               * helper files
|	|	├── favicon.ico
|	|	└── .htaccess
|	│
│   ├── fonts/                                 * font sources
|	│
│   └── data/                                  * configs and data for templates
│
└── build/                                     * built source
	├── index.html
	├── page.html
	|
	└── static/                                * static assets
		├── css/                               * minified styles
		|
		├── images/                            * minified images
		│
		├── js/                                * minified assembled js
		|
		└── fonts/                             * @font-face-ready webfonts

```

## Requirements:
- [Node.js](http://nodejs.org/)
- Build sytem: [Grunt](http://gruntjs.com/) or [Gulp](http://gulpjs.com/)
- [Bower](http://bower.io/)
- Optionally: [Editorconfig](http://editorconfig.org/)

#### Editorconfig
This project have .editorconfig file at the root that used by your code editor with editorconfig plugin. It describes codestyle like indent style, trailing whitespaces etc. See more details [here](http://editorconfig.org/)

## How to start
If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to use [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins.

If you haven't used [Gulp](http://gulpjs.com/) before, be sure to check out the [Getting Started](https://github.com/gulpjs/gulp/blob/master/docs/README.md) guide, as it explains how to use [Gulp.js](https://github.com/google/web-starter-kit/blob/master/gulpfile.js), also check these [recips](https://github.com/gulpjs/gulp/tree/master/docs/recipes#recipes) 

Before start you need to have installed _npm_ , as well as _grunt_/_gulp_ and _bower_ globally.

**A few simple steps to start:**
* Download these files. You can chose `Download zip` option or clone this repo to your local maschine.
* Now go to this project folder in terminal. Run `automation.sh` script by typing `bash automation.sh` or `sh automation.sh` and choose build system - it will extract Grunt or Gulp scripts from the `_automation` directory into project folder. Or you can manually copy all necessary files from `_automation/_build-system-name`
* Install dependencies from `package.json` by running: `npm install` and bower dependencies from `bower.json`: `bower install`. This will create `node_moduldes` and `bower_components` folders.
* Run tasks from the list below and start devevelopment! 
* Edit general settings in `dev/data/config.json` See [Site configuration](#site-configuration) section

Also `bower install` included into `start` task using shell plugin. It will install bependencies and copy them to related folder. See tasks for more details.

**bower.json dependencies**
* "jquery"
* "modernizr"

## Site configuration
This boilerplate use Pug templates with external data configs. 
Main settings can be found in `dev/data/config.json` file. And they're available for usage in templates with `config.key-name`


## Tasks
Here comes groups of grunt and gulp tasks with some explanations

#### Start 
Install bower dependencies and place them to dev folders.
Grunt: `grunt start` Gulp: `gulp start`

* Install bower components
* Copy bower components to dev folder
* Remove gitkeep files

#### Dev
Dev task with static server.
Grunt: `grunt dev` Gulp: `gulp dev`

* Compile coffescripts
* Concatenate javascripts
* Compile Sass stylesheets
* Compile Stylus stylesheets
* Add vendor prefixes in css
* Combine media queries in css files
* Compile Pug templates
* Sync helpers and other assets
* Sync fonts
* Sync images
* Run BrowserSync static server with live reload using 
* Watch for changes and run dev task


#### Build 
Build task.
Grunt: `grunt build` Gulp: `gulp build`

* Minify images
* Minify javascript files
* Minify stylesheets
* Minify html
* Run BrowserSync static server 


#### Rebuild 
Regenerate and build project by running all tasks.
Grunt: `grunt rebuild` Gulp: `gulp rebuild`

* Compile coffescripts
* Concatenate javascripts
* Compile Sass stylesheets
* Compile Stylus stylesheets
* Add vendor prefixes in css
* Combine media queries in css files
* Compile Pug templates
* Sync helpers and other assets
* Sync fonts
* Sync images
* Minify images
* Minify javascript files
* Minify stylesheets
* Minify html


#### Server 
Run server without watching for changes.
Grunt: `grunt server` Gulp: `gulp server`

* Run BrowserSync static server


#### Sprite
Sprite creation task. Should be configured before running.
Grunt: `grunt sprite:sass` Gulp: `gulp sprite:sass`

* Create images sprite and related sass files


Grunt: `grunt sprite:stylus` Gulp: `gulp sprite:stylus`

* Create images sprite and related stylus files


## Live reload 
This project uses BrowserSync as static server with enabled and configured live reload option.

## License
[MIT](http://opensource.org/licenses/MIT)
