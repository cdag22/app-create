# SDLC Navigation

0. [Home](../../README.md)
1. [Planning And Requirement Analysis](../1_PlanningAndAnalysis/README.md)
2. Defining Requirements
3. [Design and Architecture](../3_DesignAndArchitecture/README.md)

# 2. Defining Requirements: Software Requirement Specification

## Introduction

Currently there is no streamlined way for an end user to rapidly create configuration and boilerplate code for any web application in any language other than a limited number of tools in a limited number of languages/frameworks. (This is excluding applications such as [wrappler](https://wappler.io/) for building without coding). Examples of existing tools are:

- [angular-cli](https://cli.angular.io/)
- [create-react-app](https://github.com/facebook/create-react-app) 

The drawbacks to create-react-app are that it does nothing for database and server setup and is limited in its customization, e.g. it does not build a boilerplate for state management with a framework like Redux or MobX. Angular-cli is more versitile but still only allows for creation of the angular portion of the webapp and does not allow generation of code interfaced with Redux or MobX.

There are numerous boilerplates for web applications on github for specific database-framework-server combos; however, there are many combinations not covered. Furthermore, these boilerplates tend to be monolithic projects (i.e. not customizable without manual labor) and may lack maintainance, as well as require updating as libraries and best practices have changed since it was created.

The following section describes a product that seeks to fill the void of auto generating boilerplate in a highly customizable fashion for any combination of the most commonly used front-end frameworks, server-side languages, and databases.

## Product Description

1. A commandline tool for building boilerplate code for web applications in all major frontend frameworks, serverside languages, and databases. Allows for highly customizable builds via a JSON config file, or combines any of the following:
- end user code
- github/bitbucket projects or files
- cached code by the program

As a commandline tool it will accept ([all flags listed here](../../FLAGS.md)) as well as a ```config.json``` file to in which the user can ask the program to generate anything from a file to a whole project. Allows for the saving and sharing of ```config.json``` files, and boilerplate projects to hosted version control applications or on the end users system under an alias they can use as a reference for future builds or combined builds.  Allows for the option to apply code styling as specified by a style guide or code formatter. Installs all relevant packages specified.

See this link for [```config.json```](../../TEMPLATE_CONFIG.md)

2. The app will ship with a secure database for storing API Keys and senative files (e.g. AWS .pem files) that can be inserted into ```.env``` files or loaded as config files.

3. In later phases the app will have a companion site where people can search for templates, snippets, and config files by tags and title. ```app-create``` will allow for uploading of snippets, full projects, or config files to github/bitbucket. When uploading code one can optionally save data to the companion site that will include a title, hash-tags, an optional description, and a link to the version control software source. Other users of the application can then search via this companion site or command line program and then download the code.

4.  It should be noted that the design of the program is such that templates and boilerplate can be extended to include frameworks, libraries, or databases of all supported langauges by end users.

## Agile Build Process Specifications

Each phase will contain support through commandline arguments and ship with default boilerplate for those listed in their corresponding **```Config.json```**.


### 1st Iteration

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

### 2nd Iteration

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

### 3rd Iteration

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

### 4th Iteration

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

### Future Iterations

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