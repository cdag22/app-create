# Command Line Arguments

## Flags

### Informative

1. Shows man page

```bash
app-create --help -h
```

2. Lists info on the given option
```bash
app-create --list -ls [option]
```

*options*

- ```help | h``` shows all flags with a blurb
- ```formatter``` shows all formatters.
- ```lang``` lists all supported languages.
- ```saved``` shows the name of all of the users saved templates. promps a drop down that can be navigated by arrow keys to select a corresponding ```config.json``` to display on pressing enter.
- ```default``` lists names of all builtin default templates.

### Saving


3. Saves the specified ```config.json``` or if nothing is provided saves the current working directory as a boilerplate. If ```--push``` is supplied the template is pushed to the given github or bitbucket repo as well. A url must be provided.

```bash
app-create --save -s [name|config.json] --push [url]
```



*Examples*

Show all ```Java``` formatters supported

```bash
app-create --list formatter --lang Java
```

List all saved templates

```bash
app-create --list saved
```

### Basic Builds

**default usage**

4. With no flags present, builds a boilerplate from a saved one if ```[name]``` is provided or uses the specified ```config.json```. If more than one ```name``` is present and one or more ```config.json``` are present, conflit resolution is performed by giving highest prescedence to the left most argument and lowest prescedence to the right most. *NOTE* ```name``` can be a user saved template or a builtin one.

```bash
app-create [name|config.json]
```

5. Prompts the download of a config file. See [this document](./README.md) for supported sites.

```bash
app-create --import [url]
```

**Examples**

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


### Modifiers

Modifiers change priority of build parameters.

6. Used to specify a formatter to be used. Takes prescedence over any present in the supplied template(s)/config(s).

```bash
app-create [name|config.json] --formatter -f [ name ]
```

7. Gives priority of ```parameter``` to the the specified ```config.json```. Usage:

```bash
app-create name --parameter config.json
```
Parameter values can be:

- ```--application```
- ```--structure```
- ```--style```
- ```--configFiles```

See [this document](./template.json) for top level parameters.

