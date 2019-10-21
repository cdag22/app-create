# Command Line Arguments

## Flags

### CONFIG HEADERS
- --application
- --structure
- --style
- --configFiles
- --versionControl [ git | mercurial ]

### CONFIG OPTIONS
- --load [ config.json ]
- --save -s [ name ]
- --import [ github.com|bitbucket.com ]
- --combine
--default
- --formatter -f [ name ]
- --list [option, see following]
  - all
  - formatter(s)
  - lang(s)
  - template(s)
  - saved

**Examples**

```--load config.json```

```--list -lang java formatter```

```--list saved```