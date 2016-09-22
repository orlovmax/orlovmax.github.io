# Web developer business card

Built using [synt-general-template](https://github.com/synteagle/synt-general-template)

## Contents
* [Folder structure](#folder-and-file-structure)
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
├── gulp_tasks/                                * gulp tasks
|   ├── config/                                * gulp tasks config
│   |	├── paths.js
│   |	├── settings.js
│   |	└── aliases.js
│   |
|   └── task.js
│
├── gulpfile.js
└── package.json
|
├── screenshots/                               * responsive test screenshots
|
├── dev/                                       * site source
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


## Tasks
Here comes groups of grunt and gulp tasks with some explanations

#### Start 
Install bower dependencies and place them to dev folders.
Grunt: `grunt start` Gulp: `gulp start`

* Remove gitkeep files

#### Dev
Dev task with static server.
Gulp: `gulp dev`

* Concatenate javascripts
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
Gulp: `gulp build`

* Minify images
* Minify javascript files
* Minify stylesheets
* Minify html
* Run BrowserSync static server 


#### Rebuild 
Regenerate and build project by running all tasks.
Gulp: `gulp rebuild`

* Concatenate javascripts
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
Gulp: `gulp server`

* Run BrowserSync static server


#### Sprite
Gulp: `gulp sprite:stylus`

* Create images sprite and related stylus files


## Live reload 
This project uses BrowserSync as static server with enabled and configured live reload option.

## License
[MIT](http://opensource.org/licenses/MIT)
