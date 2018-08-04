# adhocore/please

`please` (aka **p**hp re**lease**) is very simple github release for PHP projects.

Assumes you like semantic versioning of the format `<major>.<minor>.<patch>`!

Actually you can release any thing not just php. Please itself is [released](https://github.com/adhocore/please/releases/tag/0.0.1) by please.

#### Working

- Determine remote git repo based on local git config
- Checkout and Update `master`
- Get latest release from github api endpoint
- Collect new commits since the latest release
- Bump the version, reflect that into `./VERSION` file and commit it
- Release the new version
- If there is `box.json` present, compile phar using `box`
  (download `box.phar` if required)
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

### Examples

```sh
please
please minor
please --vfile
please major --vfile
```

### Output

Here's output of [please](./please) in action, releasing [0.0.1](https://github.com/adhocore/please/releases/tag/0.0.1) of itself:

```
$ ./please --vfile
Repository adhocore/please
Log file /tmp/PLZEXKbyF
Updating master ...
  Done
Getting latest releases ...
  Done
Current Version 0.0.0
Collecting commits ...
  Done
Bumping version ...
  Done
Releasing 0.0.1 ...
  Done
Check /tmp/PLZEXKbyF for logs
```

#### NOTE:
- If there is `VERSION` file in project root, you dont need `--vfile` flag.
- If there is `box.json` file in project root, it builds and releases `.phar` too.
- If no scope is given, bumps the `<patch>` part of semver.
