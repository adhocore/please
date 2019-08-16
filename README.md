# adhocore/please

`please` (aka **p**hp re**lease** or even n**p**m re**lease**) is very simple Github+NPM release for ~PHP and/or Nodejs projects~ anything.

Assumes you like semantic versioning of the format `<major>.<minor>.<patch>`!

Actually you can release any thing not just PHP/Nodejs. Please itself is [released](https://github.com/adhocore/please/releases) by please.

![Help Preview](https://imgur.com/BOrHs9E.png "Help Preview")

#### Working Mechanism

- Determine remote git repo based on local git config
- Checkout and Update `master`
- Get latest release from github api endpoint
- Collect new commits since the latest release
- Create a changelog (prepend to if exists), reflect that into `./CHANGELOG.md` file and commit it
- Bump the version as per semver, reflect that into `./VERSION` file and commit it
    - If any of the latest commits start with `feat` `<minor>` is bumped
    - But if only you didnt explicitly pass `scope` already
- If there is `package.json` file, bump `package.json#version` and commit it
- If `package.json#private` is not set to `true`
    - If npm user not already logged in, run `npm adduser`
    - Run `npm publish` finally
- Release the new version and tag to github
- If there is `box.json` file, compile phar using `box`
    (download `box.phar` if required)
- Upload the compiled `phar` as asset for the recent release

## Installation

```sh
# Requirements:
# jq
sudo apt install jq -y

curl -sSLo ~/please https://raw.githubusercontent.com/adhocore/please/master/please
chmod +x ~/please && sudo ln -s ~/please /usr/local/bin/please
```

## Setup 

One time setup. In your `.bashrc` / `.zshrc` or the like export github token:

```sh 
export GH_AUTH_TOKEN=<your token here>
```

Get your token from [here](https://github.com/settings/tokens/new). 
Make sure to set only bare minimum permission scopes for this token.

### What permissions

> - [x] repo               *if you want to release private repos*
>   - [x] public_repo      *required*
>   - [x] repo_deployment  *required*

**Important**: Tokens are to be treated and kept as much secret as passwords.

## Usage and Examples

Make sure you have already merged required commits to `master` branch in Github,
then go to the root of any project you want to release and run:

```sh
please [Scope|Command] [Options]
```

```
please v0.9.0 | (c) Jitendra Adhikari | please is semver release made easy.

Usage: please [command|scope] [--options]

Commands:
  version        Print current version of itself.
  help           Show help information and usage examples.
Scope:
  major          Bumps the <major> part of semver.
  minor          Bumps the <minor> part of semver.
Options:
  -c --chlog     Forces creation of CHANGELOG.md file.
  -h --help      Show help information and usage.
  -H --chash     Prepends commit hash into log.
  -o --organize  Commit types as CSV for changelog or release notes.
                 (Default: feat,fix,refactor,perf,docs,infra,chore)
  -p --public    Set scoped npm package for public access.
  -u --update    Update _please to latest version.
  -v --vfile     Forces creation of VERSION file.
  -V --version   Forces the exact version to be released.
  -y --yes       Assume yes for any confirmation.
Events:
  --before-all   Run the command before anything (very start).
  --before-npm   Run the command before releasing to npm.
  --before-push  Run the command before pushing code to remote.
  --before-vcs   Run the command before releasing to VCS.
  --after-all    Run the command after everything finishes.
Examples:
  please
  please version                          # prints current version of itself
  please --update                         # updates please if new version available
  please --organize feat,fix,docs         # includes only features, fixes and docs
  please --vfile --chash                  # creates VERSION file, adds commit hash
  please minor --public --yes             # releases minor version without asking
  please major --vfile --chlog            # releases next major version with VERSION and CHANGELOG files
  please --vfile --chlog --version 1.5.0  # releases version 1.5.0 with VERSION and CHANGELOG files
  please --before-all 'echo {REPO}'       # before release, runs 'echo {REPO}' with REPO interpolated
```

#### Note

- If there is `VERSION` file in project root, you dont need `--vfile` flag.
- If there is `CHANGELOG.md` file in project root, you dont need `--chlog` flag.
- If there is `box.json` file in project root, it builds and releases `.phar` too.
- If no scope is given
  - If there is any `feat:` commit, bumps the `<minor>` part of semver.
  - Else bumps the `<patch>` part of semver.

### Events
You can take control of the work flow or execute more tasks by using the event callbacks.
When the event commands are triggerred they receive all the variables defined in the then moment.

Currently `please` supports five events which are executed in following order:

-  before-all
-  before-npm
-  before-push
-  before-vcs
-  after-all

You can either set events as a json file in [./please.json](./please.json) or pass them in as option to `please` like so:
```sh
# run `composer test` before pushing code
# send release notification to slack after everything finishes
please --before-push "composer test" --after-all "slack 'Released {REPO}@{NEXT_VERSION}'"
```

> The event passed in as option will have higher precedence than the one read from `./please.json`

#### Caveat
Use only single quote in the event command. Eg: `please --before-all "echo 'a b c'"`

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

And [here](https://i.imgur.com/mQaiAuk.png) is colorful screenshot of `please` releasing [v0.0.10](https://github.com/adhocore/phint/releases/v0.0.10) of [phint](https://github.com/adhocore/phint)

And here is a preview of all [features](https://www.npmjs.com/package/@adhocore/devnull) of `please` in one [release](https://github.com/adhocore/dev-null/releases/tag/0.0.6):
![Full Preview](https://imgur.com/anzTcrX.png "Full Feature Preview")

### Sample changelog

[CHANGELOG.md](./CHANGELOG.md) generated by `please` looks like:

```md
## [0.0.1](https://github.com/<repo>/releases/tag/<0.0.1>) (2018-01-01)

### Features
- **scope**: commit 1 (Author Name)
- **scope**: commit 2 (Author Name)
...
```

If you passed in `--chash` flag then:

```md
## [0.0.1](https://github.com/<repo>/releases/tag/<0.0.1>) (2018-01-01)

### Features
- **scope**: commit 1 (Author Name) [_hash1_](https://github.com/<repo>/commit/<hash1>)
- **scope**: commit 2 (Author Name) [_hash2_](https://github.com/<repo>/commit/<hash2>)
...
```

On subsequent releases new changes are prepended such that latest commits stay at top.

### Troubleshooting

If you are using `zsh` then `please` might have been already aliased to `sudo`. To fix this simply run

```sh
echo "alias please=/usr/local/bin/please" >> ~/.zshrc
source ~/.zshrc
```
