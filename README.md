
Status: Pre-Alpha! For production use wait unitl this package reaches version 1.1.3 (this will 
match the current material lite version!)

This package assumes that you are building an Angular2 app with TypeScript and Angular CLI!

[Demo](http://mseemann.github.io/angular2-mdl/)

[![CI Status](http://img.shields.io/travis/mseemann/angular2-mdl.svg?style=flat)](https://travis-ci.org/mseemann/angular2-mdl)
[![npm version](https://badge.fury.io/js/angular2-mdl.svg)](http://badge.fury.io/js/angular2-mdl)
[![Downloads](http://img.shields.io/npm/dm/angular2-mdl.svg)](https://npmjs.org/package/angular2-mdl)
[![Coverage Status](https://coveralls.io/repos/github/mseemann/angular2-mdl/badge.svg?branch=master)](https://coveralls.io/github/mseemann/angular2-mdl?branch=master)

[![Sauce Test Status](https://saucelabs.com/browser-matrix/angular2-mdl.svg)](https://saucelabs.com/u/angular2-mdl)


### Installation

```bash
npm install angular2-mdl --save
```

### How to use the scss files from material-design-lite

First of all you need to install node-sass for your project:

```bash
npm install node-sass --save-dev
```

After that you need to configure the sass compiler to use the sass files from the angular2-mdl package. 
For that the file `angular-cli-build.js` needs to be extended:

```JavaScript
return new Angular2App(defaults, {

    sassCompiler: {
      includePaths: [
        `${__dirname}/node_modules/angular2-mdl/src/scss-mdl`
      ]
    },
    vendorNpmFiles: [
      ...
      'angular2-mdl/**/*.+(js|js.map)'
    ]
  });
```

Now you can use the sass sources form angular-material-lite and change the used colors in your app:

```scss
@import "color-definitions";

$color-primary: $palette-blue-500 !default;
$color-primary-dark: $palette-blue-700 !default;
$color-accent: $palette-amber-A200 !default;
$color-primary-contrast: $color-dark-contrast !default;
$color-accent-contrast: $color-dark-contrast !default;

@import 'material-design-lite';
```




