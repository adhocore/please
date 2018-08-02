## adhocore/please

**p**hp re**lease** is very simple github release for PHP projects.

Assumes you like semantic versioning of the format `<major>.<minor>.<patch>`!

#### Working

- Determine remote git repo based on local git config
- Checkout and Update `master`
- Get latest release from github api endpoint
- Collect new commits since the latest release
- Bump the version, reflect that into `./VERSION` file and commit it
- Release the new version
- If there is `box.json` present, compile phar using `box`
  (It downloads `box.phar` if required)
- Get the ID of recent release from github api
- Upload the compiled `phar` as asset for the recent release

## Installation

```sh
# Requirements:
# jq
sudo apt install jq -y

curl -sSLo ~/please https://raw.githubusercontent.com/adhocore/please/master/please
sudo chmod +x ~/please && sudo cp ~/please /usr/local/bin/please
```

## Setup 

One time setup. In your `.bashrc` / `.zshrc` or the like export github token:

```sh 
export GH_AUTH_TOKEN=<your token here>
```

Get your token from [here](https://github.com/settings/tokens/new). 
Make sure to set only bare minimum permission scopes for this token.

**Important**: Tokens are to be treated and kept as much secret as passwords.

## Usage:

(Go to the root of any project you want to release and run)

```sh
please [Scope] [Options]
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
