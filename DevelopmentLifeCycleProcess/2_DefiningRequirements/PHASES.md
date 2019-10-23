[<-- Back](./README.md)

# Agile Build Process Specifications

Each phase will contain support through commandline arguments and ship with default boilerplate for those listed in their corresponding **```Config.json```**.


## 1st Iteration

The minimum viable product will contain customization through a ```config.json``` for

**Config.json**
  - HTML
  - CSS
    - Less
    - Sass
  - React
    - React Router
  - Redux integration
  - Webpack. With the following predefined template options
    - Isomorphic option
    - Code splitting
    - Hot reloading
  - Node
    - Express
    - Routing
  - Postgres, Sqlite3, MySql via:
    - Sequalize
    - Knex
  - Git
  - Github/Bitbucket

#### **All of the following Command Line Arguments will be supported. [See here.](../../FLAGS.md)**

## 2nd Iteration

The minimum viable product will contain customization through a config.json for

**Config.json**

- PHP: Biggest Frameworks (and vanilla? is that possible?)
  - Interfacing with SQL databases
  - Routing
- Python: Flask and Django
  - Routing
  - Interfacing with SQL databases
- Glup/Grunt
- Mercurial
- Full Webpack customization
- add support for pulling snippets from [Bit](https://github.com/teambit/bit)

## 3rd Iteration

The minimum viable product will contain customization through a ```config.json``` for

**```Config.json```**

- Ruby On Rails
  - Routing
  - sql interfacing
- all currently existing serverside integration with Mongodb and Redis
- building companion site and addition of ```--share``` flag. Companion site will have:
  - Login integration with github for connection of storing boilerplate to github
  - via the ```--share``` flag users can upload config files or links to their github boilerplate on the companion site
  - Extending the ```--import [url]``` flag to allow for downloading of ```config.json``` files from the companion site

## 4th Iteration

The minimum viable product will contain customization through a ```config.json``` for

**Config.json**

- Java in Spring/Spring Boot
  - Routing
  - all previously supported db integration
- GO
  - Routing
  - all previously supported db integration
- Apache Config
- NginX Config

## Future Iterations

Ideally builtin configs and support will eventually be provided for all of the follow.

**Frontend Frameworks**
- Backbone.js
- Ember.js
- Vue.js
- Meteor.js

**JavaScript Libraries**
- D3

**Databases**
- RDS (Amazon's SQL DB)
- CouchDB (NoSQL)
- Neo4j (NoSQL; Graph)