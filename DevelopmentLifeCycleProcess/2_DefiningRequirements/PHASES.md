[<-- Back](./README.md)

# Agile Build Process Specifications

Each phase will contain support through commandline arguments and ship with default boilerplate for those listed in their corresponding **```Config.json```**.

## 1st Iteration

The minimum viable product will allow for easily creating a custom project from scratch. ```config.json``` will not be supported yet. Either in a empty Github repo or through connecting an empty project to a github repo.

It will be Node based and allow for quickly installing npm packages automatically.

It will support basic configuration and some template for Webpack, React, vanilla JS, jQuery, HTML, and CSS.

CSS templates will be either raw CSS, Sass, Less, or Styled Components. It will allow for integration, templates, and setup with Bootstrap, Materialize, Foundation, UIKit, and Semantic UI Frameworks.

It will come with predefined options of quick insertion for color templates, or create of color templates.

It will implement the template tagging system for saved templates.

It will at the bear minimum require:
  - Setup of an ```index.html```
  - Creation of one CSS file
  - Creation of all bear minimum JavaScript Files based on whether the project is:
    * Vanilla JavaScript
    * jQuery
    * React (along with the requirement of a basic Webpack File; and question about where to install babel config. Default is .babelrc)

It will allow for the customization of the default questions asked through the flag ```--config``` which will take in either **css**, **html**, **js**, or **gui**. If **gui** is entered then a configuration menu will pop up with options to set a custom profile.


## 2nd Iteration

The minimum viable product will contain customization through a ```config.json``` for

**```Config.json```**

  - HTML: Templates
  - CSS: Less, Sass
  - React
    - React Router
    - Higher Level Components?
  - Redux integration
  - Full Webpack customization, with the following predefined template options:
    - Isomorphic option
    - Code splitting
    - Hot Reloading
    - (What else?)
  - Node
    - Express
    - Routing
  - Postgres, Sqlite3, MySql via:
    - Sequalize
    - Knex
  - Git
  - Github

#### **All of the following Command Line Arguments will be supported. [See here.](../../FLAGS.md)**

## 3rd Iteration

The minimum viable product will contain customization through a config.json for

**```Config.json```**

- Next.js
- Gatsby.js
- GraphQL
- GraphQL Apollo
- Gulp/Grunt Configuration (any other build tools?)
- Mercurial
- BitBucket
- add support for pulling snippets from [Bit](https://github.com/teambit/bit)

## 4th Iteration --> Adding Three Server-side Languages and Apache/NginX Support

The minimum viable product will contain customization through a ```config.json``` for

**```Config.json```**

- Apache and NginX Config and Support
- Support for SQL databases for Three new languages
- Support for GraphQL and Apollo for Three new languages
- Routing for Three new Languages
- New Languages:
    - PHP: Biggest Frameworks (and vanilla? is that possible?)
    - Python: Flask and Django
    - Ruby On Rails

## 5th Iteration --> Adding Five biggest (excluding React.js) Front-end Frameworks

The minimum viable product will contain customization through a ```config.json``` for

**```Config.json```**

- Adding configuration between each server-side Language and the following front-end Frameworks:
    - Angular.js
    - Vue.js
    - Meteor.js
    - Backbone.js
    - Ember.js
- Adding support for all Frameworks between GraphQL, Redux and the new one MobX

## 6th Iteration --> Companion Site

- building companion site and addition of ```--share``` flag. Companion site will have:
    - Login integration with github for connection of storing boilerplate to github
    - via the ```--share``` flag users can upload config files or links to their github boilerplate on the companion site
    - Extending the ```--import [url]``` flag to allow for downloading of ```config.json``` files from the companion site

## 7th Iteration --> Three more Serverside Languages

The minimum viable product will contain customization through a ```config.json``` for

**```Config.json```**

- Support for SQL databases for Three new languages
- Support for GraphQL and Apollo for Three new languages
- Routing for Three new Languages
- Framework integration for all existing combinations
- Languages:
    - Java in Spring/Spring Boot
    - GO (frameworks?)
    - C# and .NET (frameworks?)

## 8th Iteration --> Adding Integration with NoSQL Databases

The minimum viable product will contain customization through a ```config.json``` for

**```Config.json```**

- Add boilerplate for all server-side languages for:
    - MongoDB
    - Redis
    - Neo4j
    - Any others?

## Future Iterations

Ideally builtin configs and support will eventually be provided for all of the follow.

**JavaScript Libraries**
- D3

**Databases**
- RDS (Amazon's SQL DB)
- CouchDB (NoSQL)