# angular-hero-app
Deploy Angular 2 Hero Tutorial in Github pages

## angular-cli-ghpages

Using *angular-cli-ghpages* npm dependency to deploy to gh-pages branch.
* [Angular hero app](https://ricardogarfe.github.io/angular-hero-app/)

This dependecy *deploys your dist directory into gh-pages branch*, that's the magic behind it

## Continuous Deployment

You can automate deployment using travis-ci

```yml
language: node_js

node_js:
  - "7"

cache:
  directories:
  - node_modules

install:
  - npm i --silent --no-optional -g @angular/cli
  - npm i --silent --no-optional -g angular-cli-ghpages
  - npm install

before_script:
  - ng build --prod --base-href "https://ricardogarfe.github.io/angular-hero-app/"

script:
  angular-cli-ghpages --repo=https://GH_TOKEN@github.com/ricardogarfe/angular-hero-app.git --branch gh-pages --name="Ricardo García Fernández" --email=ricardogarfe@gmail.com
```


