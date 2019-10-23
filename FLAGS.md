### SDLC Navigation

0. [Home](./README.md)
1. [Planning And Requirement Analysis](./DevelopmentLifeCycleProcess/1_PlanningAndAnalysis/README.md)
2. [Defining Requirements](./DevelopmentLifeCycleProcess/2_DefiningRequirements/README.md)
3. [Design and Architecture](./DevelopmentLifeCycleProcess/3_DesignAndArchitecture/README.md)
4. Building
5. Testing
6. Deployment
7. [Example Output](./DevelopmentLifeCycleProcess/7_ExampleOutput/README.md)
8. Usage

---

# 8. Usage

## Flags

### 1. Informative

A. Shows man page

```bash
app-create --help -h
```

B. Lists info on the given option

```bash
app-create --list -ls [option]
```

*options*

- ```help | h``` shows all flags with a blurb
- ```formatter``` shows all formatters.
- ```lang``` lists all supported languages.
- ```saved``` shows the name of all of the users saved templates. promps a drop down that can be navigated by arrow keys to select a corresponding ```config.json``` to display on pressing enter.
- ```default``` lists names of all builtin default templates.

C. *Examples*

Show all ```Java``` formatters supported

```bash
app-create --list formatter --lang Java
```

List all saved templates

```bash
app-create --list saved
```

### 2. Saving Locally and Remotely


A. Saves the specified ```config.json``` or if nothing is provided saves the current working directory as a boilerplate. If ```--push``` is supplied the template is pushed to the given github or bitbucket repo as well. A url must be provided.

```bash
app-create --save -s [name|config.json] --push [url]
```

B. Saves the specified ```config.json``` or locally saved boilerplate called ```name``` or if nothing is provided the current working directory to github/bitbucket and creates a link to it on the companion site.
  - Prompts the user through the standard git remote push workflow.
  - Prompts the user to enter at least three tags. Provides suggestions.
  - Prompts the user if they want to post to the companion site with a description.

*NOTE* ```url``` must be provided and be a valid empty github, bitbucket repository.

```bash
app-create --share OPTIONAL:[name|config.json] [url]
```

### 3. Basic Builds

A. **default usage: With no flags present,** builds a boilerplate from a saved one if ```[name]``` is provided or uses the specified ```config.json```. If more than one ```name``` is present and one or more ```config.json``` are present, conflit resolution is performed by giving highest prescedence to the left most argument and lowest prescedence to the right most. *NOTE* ```name``` can be a user saved template or a builtin one.

```bash
app-create [name|config.json]
```

B. Prompts the download of a config file, project or file. See [this document](./README.md) for supported sites.

```bash
app-create --import [url]
```

Can be combined with basic usage like so:

```bash
app-create [any number of name|config.json] --import [url] [any number of name|config.json]
```

C. *Examples*

```bash
app-create config.json
```

```bash
app-create express-mongo-react-redux
```

```bash
app-create express-postgres-with-router config.json --formatter eslint:standard
```

```bash
app-create one.json two.json
```




### 5. Modifiers

Modifiers change priority of build parameters.

A. Used to specify a formatter to be used. Takes prescedence over any present in the supplied template(s)/config(s).

```bash
app-create [name|config.json] --formatter -f [ name ]
```

B. Gives priority of ```parameter``` to the the specified ```config.json```. Usage:

```bash
app-create name --parameter config.json
```
Parameter values can be:

- ```--application```
- ```--structure```
- ```--style```
- ```--configFiles```

*See [this document](./template.json) for top level parameters.*

