## adhocore/please

**p**hp re**lease** is very simple github release for PHP projects.

Assumes you like semantic versioning of the format `<major>.<minor>.<patch>`!

## Installation:

```sh
curl -sSLo ~/please https://raw.githubusercontent.com/adhocore/please/master/please
sudo chmod +x ~/please && sudo cp ~/please /usr/local/bin/please
```

## Setup 

One time setup. In your .bashrc or .zshrc or the like export github token:

```sh 
export GH_AUTH_TOKEN=<your token here>
```

Get your token from [here](https://github.com/settings/tokens/new). 
Make sure to set only bare minimum permission scopes for this token.

**Important**: Tokens are to be treated and kept as much secret as passwords.

## Usage:

(Go to the root of any project you want to release and run)

```sh
release [Scope] [Options]
```
### Scope

```
major     Bumps the <major> part of semver.
minor     Bumps the <minor> part of semver.
```

### Options

```
--vfile   Forces creation of VERSION file (if it doesnt exist) with next version as content.
```

### Examples:

```sh
please
please minor
please --vfile
please major --vfile
```

#### NOTE:
- If there is `VERSION` file in project root, you dont need `--vfile` flag.
- If there is `box.json` file in project root, it builds and releases `.phar` too.
- If no scope is given, bumps the `<patch>` part of semver.
