# Laravel Bootstrap

This is a personal Laravel Bootstrap, by [Escape Criativação](http://www.escape.ppg.br).

### Installation

```sh
$ git clone git@github.com:escapecriativacao/laravel-bootstrap.git [your-project-name] && cd $_ && rm -rf .git
$ composer install
$ php artisan key:generate
$ npm install
```

This command will:

* Clone this repository;
* Install composer dependencies;
* Install npm dependencies;
* Generate Laravel key;

***

### Assets

This bootstrap utilizes [SASS](http://sass-lang.com/), [Compass](http://compass-style.org/) and [Grunt](http://gruntjs.com/). So you will need:

* [NodeJS](http://nodejs.org/)
  * [Grunt](http://gruntjs.com/) `$ [sudo] npm install -g grunt-cli`
* [Ruby](https://www.ruby-lang.org/)
  * [SASS](http://sass-lang.com/) `$ [sudo] gem install sass`
  * [Compass](http://compass-style.org/) `$ [sudo] gem install compass --pre`

To compile and watch for changes in your assets, run:

```sh
$ grunt
```

If you get an error message like `Error: invalid option: --sourcemap`, please remove your existing compass version and install with the option `--pre`.

```
$ [sudo] gem install compass --pre
```

#### Assets structure

##### SCSS

public/stylesheets/scss
```
├── main.scss (import all the files in the tree)
├── components
│   ├── _buttons.scss
│   ├── _font-face.scss
│   ├── _forms.scss
│   └── _helpers.scss
├── core
│   ├── _general.scss
│   ├── _header.scss
│   ├── _content.scss
│   └── _footer.scss
├── global
│   ├── _variables.scss
│   └── _mixins.scss
├── sections
│   └── home.scss
├── vendor
│   └── _normalize.scss
```

The main.css file includes [sourcemaps](https://developer.chrome.com/devtools/docs/css-preprocessors), which makes easier to identify CSS rules in the developer tools.

All this files compile to the `public/stylesheets/css` folder.

### After Install

We use `psr-4` for autoloading the app classes, and the default namespace is `App`. If you want to change that, you will need:

* The `namespace` declaration in every file inside the `app/src` folder;
* The `autoload` declaration in the `composer.json` file;
* The `namespace` declaration in the `app/routes.php` file;
* The `namespace` declaration in the `app/src/Providers/ErrorsServiceProvider.php` file;

***

### Things you may want to change

* The default environment detection is mapped to `*.local`. You may want to change this in the `bootstrap/start.php` file.
* This bootstrap uses [laravel-asset-versioning](https://github.com/EscapeWork/laravel-asset-versioning) version the assets in production. If you don't want to use this package, just remove in the `composer.json` file and the `app/config/app.php` providers array.

### Font-face generation

This repository has the grunt [fontgen](https://github.com/agentk/grunt-fontgen) package installed via npm. If you want to generate some font-faces with a easy way, please do the following:

* Check if your system has the [package](https://github.com/agentk/grunt-fontgen) requeriments;
* Put all your `.otf` and `.ttf` files in the `public/assets/stylesheets/css/fonts` directory;
* Uncomment all `fontgen` comments in `Gruntfile.js`;
* Run `$ grunt generate-font-faces`;
* All your font-faces files need to be in your `public/assets/stylesheets/css/fonts` (including CSS);

### Components

* [Laravel 4](http://laravel.com/)
* [LaravelHelpers](https://github.com/EscapeWork/LaravelHelpers)
* [SASS](http://sass-lang.com/) with [Compass](http://compass-style.org/);
* [Normalize CSS](http://necolas.github.io/normalize.css/);
* [jQuery](http://jquery.com/);
* [Modernizr](http://modernizr.com/);
* [HTML5 Boilerplate](http://html5boilerplate.com/);
* [Grunt Fontgen](https://github.com/agentk/grunt-fontgen);
* [PHP Dontenv](https://github.com/vlucas/phpdotenv);

***

### License

#### The MIT License (MIT)

Copyright (c) 2013 Escape Criativação LTDA

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.