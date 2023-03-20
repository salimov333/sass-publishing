# SASS and publishing

## Definitions:

- Sass is a preprocessor scripting language that is interpreted or compiled into Cascading Style Sheets.
- Sass stands for Syntactically Awesome Stylesheet.
- Sass is an extension to CSS.
- Sass is a CSS pre-processor.
- Sass is completely compatible with all versions of CSS.
- Sass reduces repetition of CSS and therefore saves time
- Sass lets you reuse your code, split it into files, and it also helps you create functions, variables, nest your CSS selectors, and other shortcuts

- The term SCSS is an acronym for Sassy Cascading Style Sheets. It is basically a more advanced and evolved variant of the CSS language. Natalie Weizenbaum and Chris Eppstein created it, and Hampton Catlin designed it. It comes with more advanced features- thus often called Sassy CSS.

## The most important difference between SCSS and original Sass

### SCSS

* Syntax is similar to CSS (so much that every regular valid CSS3 is also valid SCSS, but the relationship in the other direction obviously does not happen)
* Uses braces {}
* Uses semi-colons ; 
* Assignment sign is :
* To create a mixin it uses the @mixin directive
* To use mixin it precedes it with the @include directive
* Files have the .scss extension.

### Original Sass

* Syntax is similar to Ruby
* No braces
* No strict indentation
* No semi-colons
* Assignment sign is = instead of :
* To create a mixin it uses the = sign
* To use mixin it precedes it with the + sign
* Files have the .sass extension.

## Create a Sass Project

- Create a new public repository on GitHub (Do not add a README file)
- Create the project folder on your Computer.
- Create index.html, main.scss, README.md and add your code.

```bash
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:<<Your-GitHb-Username>>/<<Repository-Name>>.git
git push -u origin main
```

```bash
npm init -y
npm install --save-dev sass
npm install bootstrap
```
- Remove the "main" field in package.json
- Create .gitignore and add node_modules
- Install a VSC extension => live Sass Compiler
- To Run the compiler => Click on watch Sass
- Open the index.html file in the Browser 
- Modify the main.scss

## Compile and watch SASS in command line.
```bash
sudo apt install ruby-sass
sass --watch main.scss:main.css
```
**Or add to package.json**
- New script: "start": "sass --watch main.scss main.css"
```bash
npm start
```

## Publishing
### Using GitHub pages:
- [About GitHub Pages](https://docs.github.com/en/enterprise-server@3.6/pages/getting-started-with-github-pages/about-github-pages)

### Using gh-pages and parcel packages
```bash
npm install --save-dev gh-pages parcel
```
**Add to package.json**
- New script: "build": "parcel build index.html --dist-dir build --public-url ./"
- New script: "deploy": "gh-pages -d build"

```bash
git add . && git commit -m "ready to deploy"
git push
npm run build
npm run deploy
```