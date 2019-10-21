# Command Line Arguments

## Flags

### Informative

 Shows man page
```bash
app-create --help -h
```

Specifies a language. See [this document](./README.md) for what languages are supported currently.

```bash
app-create --lang -l [name]
```

Lists info on the given option
```bash
app-create --list -ls [option]
```

*options*

- ```help | h``` shows all flags with a blurb
- ```formatter``` shows all formatters.
- ```lang``` lists all supported languages.
- ```saved``` shows the name of all of the users saved templates. promps a drop down that can be navigated by arrow keys to select a corresponding ```config.json``` to display on pressing enter.

Saves the specified ```config.json``` or if nothing is provided saves the current working directory as a boilerplate.

```bash
app-create --save -s [name] [OPTIONAL: config.json]
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

With no flags present, builds a boilerplate from a saved one if ```[name]``` is provided or uses the specified ```config.json```. If both ```name``` and one or more ```config.json``` are present, conflit resolution is performed by giving prescedence to ```name``` then the config files in order from left to right.

```bash
app-create [name|config.json]
```

Used to specify a formatter to be used. Ignored if one is present in the supplied ```name``` or ```config.json```.

```bash
app-create [name|config.json] --formatter -f [ name ]
```

Prompts the download of a config file. See [this document](./README.md) for supported sites.

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


### Modifiers - change priority of build parameters

Gives priority to the named formatter over the specified template/config(s).

```bash
app-create [name|config.json] --formatter [name] --priority
```

Gives priority of ```parameter``` to the the specified ```config.json```. Usage:

```bash
app-create name --parameter config.json
```
Parameter values can be:

- ```--application```
- ```--structure```
- ```--style```
- ```--configFiles```

See [this document](./template.json) for top level parameters.

