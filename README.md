# Brunch with Bootstrap 4 Example

## First things first
This repository is an example for my Brunch.io setup with Bootstrap 4. I used the [Modern JS](https://github.com/brunch/with-es6) skeleton as boilerplate to start.

## Installation

## Getting started

Note: installation is based on OS X, for other systems please see the respective documentations.

* Install (if you don't have them):
    * [Node.js](http://nodejs.org): `brew install node`
    * [Yarn](https://yarnpkg.com/lang/en/): `brew install yarn`
    * [Brunch](http://brunch.io): `yarn install -g brunch`
    * Run `yarn install` to install all packages
* Run:
    * `yarn start` — watches the project with continuous rebuild. This will also launch HTTP server with [pushState](https://developer.mozilla.org/en-US/docs/Web/Guide/API/DOM/Manipulating_the_browser_history).
    * `yarn run build` — builds minified project for production
* Learn:
    * `public/` dir is fully auto-generated and served by HTTP server.  Write your code in `app/` dir.
    * Place static files you want to be copied from `app/assets/` to `public/`.
    * [Brunch site](http://brunch.io), [Getting started guide](https://github.com/brunch/brunch-guide#readme)


## Important
Please note the options for the sass plugin in brunch-config.js
Without the option `precision: 8` the compiling doesn't work. You'll just get the warning "sass-brunch is taking too long to compile" over and over again.


## Directory structure

```
├── app/
│   ├── assets/
│   ├── js/
│   ├── scss/
│       ├── bootstrap/
│           ├── _config.scss
│       ├── _variables.scss
│   ├── index.scss
```

### assets
Everything here gets copied exactly as it is to public. Put .html files here.

### scss
In `_variables.scss` I define custom variables which aren't provided in Bootstrap.

#### bootstrap

`config.scss`
Bootstrap can be used very modular. I use `import` in `config.scss` to only the modules of Bootstrap  I like to use instead of the whole bunch.

## Javascript
Bootstrap 4 comes with custom jQuery plugins which comes in handy. They're imported in index.js.
