# SDLC Navigation

1. [Planning And Requirement Analysis](./DevelopmentLifeCycleProcess/1_PlanningAndAnalysis/README.md)
2. Defining Requirements
3. [Design and Architecture](./DevelopmentLifeCycleProcess/3_DesignAndArchitecture/REAME.md)

# 2. Defining Requirements: Software Requirement Specification

## Introduction

Currently there is no streamlined way for an end user to rapidly create configuration and boilerplate code for any web application in any language other than a limited number of tools in a limited number of languages/frameworks. (This is excluding applications such as [wrappler](https://wappler.io/) for building without coding). Examples of existing tools are:

- [angular-cli](https://cli.angular.io/)
- [create-react-app](https://github.com/facebook/create-react-app) 

The drawbacks to create-react-app are that it does nothing for database and server setup and is limited in its customization, e.g. it does not build a boilerplate for state management with a framework like Redux or MobX. Angular-cli is more versitile but still only allows for creation of the angular portion of the webapp and does not allow generation of code interfaced with Redux or MobX.

There are numerous boilerplates for web applications on github for specific database-framework-server combos; however, there are many combinations not covered. Furthermore, these boilerplates tend to be monolithic projects (i.e. not customizable without manual labor) and may lack maintainance, as well as require updating as libraries and best practices have changed since it was created.

The following section describes a product that seeks to fill the void of auto generating boilerplate in a highly customizable fashion for any combination of the most commonly used front-end frameworks, server-side languages, and databases.

## Product Description

A commandline tool for building boilerplate code for web applications in all major frontend frameworks, serverside languages, and databases. Allows for highly customizable builds via a JSON config file, or combines any of the following:
- end user code
- github boilerplate
- cached code by the program

Allows for the saving and sharing of ```config.json``` files, and boilerplate projects to hosted version control applications or on the end users system under an alias they can use as a reference for future builds or combined builds.  Allows for the option to apply code styling as specified by a style guide or code formatter. Installs all relevant packages specified.

A ```config.json``` file will look something like [this](../../template.json) As a commandline tool it will take flags and options as well as an optional ```config.json``` file determine what the end user would like to be performed.


## Agile Build Process Specifications

Each phase will contain support through commandline arguments and ship with default boilerplate for those listed in their corresponding **```Config.json```**.


### Initial Spec

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

**Supported Commandline Arguments [Here](../../FLAGS.md)**

### Second Iteration

The minimum viable product will contain customization through a config.json for

**Config.json**

- PHP
  - Interfacing with SQL databases
  - Routing
- Python: Flask and Django
  - Routing
  - Interfacing with SQL databases
- Glup/Grunt
- Mercurial
- Full Webpack customization

### Third Iteration

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

### Fourth Iteration

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