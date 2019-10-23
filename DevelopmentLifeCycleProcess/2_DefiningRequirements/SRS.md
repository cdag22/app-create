[<-- Back](./README.md)

# Software Requirement Specification

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



2. The app will ship with a secure database for storing API Keys and senative files (e.g. AWS .pem files) that can be inserted into ```.env``` files or loaded as config files.

3. In later phases the app will have a companion site where people can search for templates, snippets, and config files by tags and title. ```app-create``` will allow for uploading of snippets, full projects, or config files to github/bitbucket. When uploading code one can optionally save data to the companion site that will include a title, hash-tags, an optional description, and a link to the version control software source. Other users of the application can then search via this companion site or command line program and then download the code.

4.  It should be noted that the design of the program is such that templates and boilerplate can be extended to include frameworks, libraries, or databases of all supported langauges by end users.

## Interfaces

### User Interface

As a commandline tool it will accept ([all flags listed here](../../FLAGS.md)) as well as a ```config.json``` file to in which the user can ask the program to generate anything from a file to a whole project. Allows for the saving and sharing of ```config.json``` files, and boilerplate projects to hosted version control applications or on the end users system under an alias they can use as a reference for future builds or combined builds.  Allows for the option to apply code styling as specified by a style guide or code formatter. Installs all relevant packages specified. See this link for the details of the [```config.json```](../../TEMPLATE_CONFIG.md) feed into the application.

### Internal Interface

As a commandline utility it will interface with the end user's Operating System to store files, and directories while using an internal tagging system. It will maintain an internal database that tracks file extensions, frameworks, template names, names of formatters, configuration files, and the users configuration for a specific database (e.g. logins/passwords to their local postgres instance). It will track framework types by prompting a user on save to select from a list or add to the list a front-end and/or back-end framework as well as any ORMs/Query Builders the template uses. It will store all this information in an SQL database according to [this]() detailed schema.

## Failure Conditions

### Invalid Flag Usage

1. **Invalid Flag or Flag combination** If a user enters an invalid flag or unacceptable combination of flags the program will respond with a brief list of all primary flags it accepts.

### Invalid Input Type

1. **Invalid Names** If a user enters a name of a template that does not exist the program will respond with the name it does not recongize and the command to list all templates builtin or custom built and saved by the user cached on the user's system.
2. **Invalid ```config.json```** If the format of the ```config.json``` is incorrect the program will halt execution at the point in parsing the file it did not understand the input, and display the input to the user. It will also contain a link to the GitHub Repo Config Tempate markdown file containing all acceptable keys and values.
3. **Invalid url** If the user is attempting to fetch or upload a url or template the program will print out the url and list the bases of urls of all accepted sites; i.e. GitHub or BitBucket.

### Naming Collisions

1. **Local Name Collision** If a user attempts to save something under a name that is already in use the program will respond with a brief message and list all named templates sorted on the users machine.
2. **Download Name Collision** If a user attempts to download a template that has an identical name to one on their machine the program will respond with a warning and ask the user to enter a different name for the downloaded template after displaying the names of all saved templates.

## One-time Operations and Initial Execution

Upon intial installation and first use, the user will be prompted to do nothing. The first time a user attempts to push code, or fetch code the user will be prompted to enter their GitHub handle and password before the first execution takes place.

## Limitations

The program will be limited by the storage space of the end user's machine and their RAM. The program will not store tempates in a database since that may load to much data into the user's RAM. Instead templates will be assembled from parts, or as wholes cached on the users system and copied to the desired location.