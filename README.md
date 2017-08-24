# Brunch with Bootstrap 4  in my favored SCSS setup <sup>*)</sup>
<sup>*)</sup> for small to medium projects

## First things first
This repository is an example for my Brunch.io setup with Bootstrap 4. I used the [Modern JS](https://github.com/brunch/with-es6) skeleton as boilerplate to start. I‘m using a specific setup and structure for my Bootstrap and SCSS in this repo. It's my currently favored setup for small to medium projects.

This repository serves as an example for my two articles I wrote:
* [Setting up Brunch with Bootstrap 4](https://medium.com/@programmiri/setting-up-brunch-with-bootstrap-4-ca052e513e4)
* [My favored SCSS setup with Bootstrap 4](no link yet)


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
│           ├── _pre_defaults.scss
│       ├── bootstrap_ext/
│           ├── _button.scss
│       ├── _variables.scss
│   ├── index.scss
│   ├── index.js
```

### assets
Everything here gets copied exactly as it is to public. Put .html files here.

### js
Bootstrap 4 comes with custom jQuery plugins which comes in handy. They're impoted in index.js.

### SCSS
There shouldn't be any SCSS files directly in this directory other than the _variables.scss. I prefer to use the variables which are provided by Bootstrap. Only in cases there’s nothing to be used from the Bootstrap core, I declare a custom variable in `_variables.scss`

__Directory bootstrap__

`config.scss`
Bootstrap can be used very modular. I don’t import the complete Bootstrap CSS. Instead I use import in the `_config.scss `to only get the components I want to use.

`pre_default.scss`
Bootstrap uses `!default` on each variable, which makes customizing very easy. It's the oposite of the notorious `!import`: While `!important` is like "Oh, there's a rule for this? I don't care, use this!", a variable with `!default` will only get defined by sass if it isn't already set. So if I want to change a Bootstrap variable, I do so in the `_pre_default.scss` file.

You can find an example in this repo!

__Directory bootstrap_ext__
I customize and extend styles in Bootstrap in separate files, which are stored in a special folder. The file is named like the Bootstrap component I’m changing or extending.

You can find an example this repo: the file `_button.scss`

__index.scss__
All scss components come together here via import. I don't declare any styles here!

__index.js__
All Javascript modules get imported and initialized here.

### Further structure
From here it’s up to you how to create your structure :)


