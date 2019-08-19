## [0.9.4](https://github.com/adhocore/please/releases/tag/0.9.4) (2019-08-19)

### Bug Fixes
- Update version of please in the repo instead of running binary (Jitendra Adhikari) [_1a914a8_](https://github.com/adhocore/please/commit/1a914a8)


## [0.9.3](https://github.com/adhocore/please/releases/tag/0.9.3) (2019-08-19)

### Bug Fixes
- No need to bump version on update anymore (Jitendra Adhikari) [_e3bb660_](https://github.com/adhocore/please/commit/e3bb660)

### Internal Refactors
- Dont use curly brace when not needed (Jitendra Adhikari) [_e4ba164_](https://github.com/adhocore/please/commit/e4ba164)

### Documentations
- Add info about before-phar (Jitendra Adhikari) [_eefd73d_](https://github.com/adhocore/please/commit/eefd73d)

### Miscellaneous
- Add/support before-phar event (Jitendra Adhikari) [_487f372_](https://github.com/adhocore/please/commit/487f372)
- Cleanup and minify code (Jitendra Adhikari) [_2712d1a_](https://github.com/adhocore/please/commit/2712d1a)
- Update release commit (Jitendra Adhikari) [_b8bf707_](https://github.com/adhocore/please/commit/b8bf707)


## [0.9.2](https://github.com/adhocore/please/releases/tag/0.9.2) (2019-08-16)

### Bug Fixes
- Make sure ./please is staged before push (Jitendra Adhikari) [_eea3631_](https://github.com/adhocore/please/commit/eea3631)


## [0.9.1](https://github.com/adhocore/please/releases/tag/0.9.1) (2019-08-16)

### Bug Fixes
- Event trigger eval (Jitendra Adhikari) [_a0f3d47_](https://github.com/adhocore/please/commit/a0f3d47)


## [0.9.0](https://github.com/adhocore/please/releases/tag/0.9.0) (2019-08-16)

### Features
- Read events from please.json (can still be overridden by params) (Jitendra Adhikari) [_18512d5_](https://github.com/adhocore/please/commit/18512d5)
- Support registering events and trigger them during lifecycle (Jitendra Adhikari) [_5d0e469_](https://github.com/adhocore/please/commit/5d0e469)

### Bug Fixes
- Version and before-push (Jitendra Adhikari) [_037a58c_](https://github.com/adhocore/please/commit/037a58c)
- Trim leading -- from event name (Jitendra Adhikari) [_6a46030_](https://github.com/adhocore/please/commit/6a46030)

### Internal Refactors
- Update usage info, rename --before-github to --before-vcs (Jitendra Adhikari) [_262bf28_](https://github.com/adhocore/please/commit/262bf28)

### Documentations
- Update usage info, add events section (Jitendra Adhikari) [_61a8994_](https://github.com/adhocore/please/commit/61a8994)

### Miscellaneous
- Add please.json (Jitendra Adhikari) [_933e791_](https://github.com/adhocore/please/commit/933e791)


## [0.8.1](https://github.com/adhocore/please/releases/tag/0.8.1) (2019-08-07)

### Bug Fixes
- Info => echo (Jitendra Adhikari)


## [0.8.0](https://github.com/adhocore/please/releases/tag/0.8.0) (2019-08-07)

### Features
- Add version command, bump version on --update (Jitendra Adhikari)

### Documentations
- Update --help output (Jitendra Adhikari)


## [0.7.1](https://github.com/adhocore/please/releases/tag/0.7.1) (2019-08-03)

### Bug Fixes
- Use RANGE instead of DIFF (Jitendra Adhikari) [_d56c77d_](https://github.com/adhocore/please/commit/d56c77d)

### Internal Refactors
- Remove UTC in changelog, use direct curl to release, relocate bump info (Jitendra Adhikari) [_cffbb1e_](https://github.com/adhocore/please/commit/cffbb1e)


## [0.7.0](https://github.com/adhocore/please/releases/tag/0.7.0) (2019-08-03) UTC

### Features
- Support -o|--organize option to control changelog (Jitendra Adhikari) [_062c513_](https://github.com/adhocore/please/commit/062c513)
- Organize commits by type (Jitendra Adhikari) [_de961ba_](https://github.com/adhocore/please/commit/de961ba)

### Bug Fixes
- Push to deploy branch (Jitendra Adhikari) [_6c83e0d_](https://github.com/adhocore/please/commit/6c83e0d)
- Support https origin url (Jitendra Adhikari) [_37a2699_](https://github.com/adhocore/please/commit/37a2699)
- Change release header to [version] (date) (Jitendra Adhikari) [_07ec9b9_](https://github.com/adhocore/please/commit/07ec9b9)

### Internal Refactors
- Prepare travis support, skip update if current branch is deploy branch (Jitendra Adhikari) [_ceb61da_](https://github.com/adhocore/please/commit/ceb61da)
- Place commit hash at last (Jitendra Adhikari) [_1ba31fe_](https://github.com/adhocore/please/commit/1ba31fe)

### Documentations
- Include --organize option (Jitendra Adhikari) [_2bdefa3_](https://github.com/adhocore/please/commit/2bdefa3)
- Update changelog sample (Jitendra Adhikari) [_22e918d_](https://github.com/adhocore/please/commit/22e918d)


## [0.6.1] 2019-08-02 15:08:21 UTC

- [aa92bc6](https://github.com/adhocore/please/commit/aa92bc6) fix: check git repo after parsing args (Jitendra Adhikari)

## [0.6.0] 2019-08-02 14:08:33 UTC

- feat(box): use box.phar version according as php version (Jitendra Adhikari) | [23edd43](https://github.com/adhocore/please/commit/23edd43)

## [0.5.0] 2019-07-21 05:07:51 UTC

- [1241b7a](https://github.com/adhocore/please/commit/1241b7a) docs: about --version/-V (Jitendra Adhikari)
- [a7c0a11](https://github.com/adhocore/please/commit/a7c0a11) feat(please): possibility to release exact version (Jitendra Adhikari)

## [0.4.0] 2019-07-16 06:07:43 UTC

- [9a029e9](https://github.com/adhocore/please/commit/9a029e9) chore: print new release url after released (Jitendra Adhikari)
- [8285835](https://github.com/adhocore/please/commit/8285835) feat: aggregate chore commits (Jitendra Adhikari)

## [0.3.5] 2019-01-29 07:01:39 UTC

- [fc69229](https://github.com/adhocore/please/commit/fc69229) fix: git push after npm-publish last (Jitendra Adhikari)

## [0.3.4] 2018-10-04 14:10:00 UTC

- [3ae11a2](https://github.com/adhocore/please/commit/3ae11a2) fix(please): use single quote instead of double in json body [fixes #13] (Jitendra Adhikari)

## [0.3.3] 2018-09-12 13:09:42 UTC

- [c6f1094](https://github.com/adhocore/please/commit/c6f1094) fix(please): npm publish skip if private (Jitendra Adhikari)

## [0.3.2] 2018-09-11 10:09:53 UTC

- fix(please): use readlink instead (Jitendra Adhikari)

## [0.3.1] 2018-09-07 11:09:33 UTC

- [36e0804](https://github.com/adhocore/please/commit/36e0804) fix(please): handle v prefix in major bump [closes #10] (Jitendra Adhikari)

## [0.3.0] 2018-08-25 15:08:45 UTC

- [765922d](https://github.com/adhocore/please/commit/765922d) docs(readme): --yes [closes #9] (Jitendra Adhikari)
- [e3e99c9](https://github.com/adhocore/please/commit/e3e99c9) feat(please): add confirmation prompt with --yes option (Jitendra Adhikari)

## [0.2.1] 2018-08-19 13:08:26 UTC

- [20cc9b9](https://github.com/adhocore/please/commit/20cc9b9) fix(please): quoted interpolation when empty (Jitendra Adhikari)
- [cedde9a](https://github.com/adhocore/please/commit/cedde9a) docs: update preview img. add change log author name (Jitendra Adhikari)
- [16ecfbd](https://github.com/adhocore/please/commit/16ecfbd) docs: update help preview (Jitendra Adhikari)

## [0.2.0] 2018-08-18 10:08:19 UTC

- [ef9b8f0](https://github.com/adhocore/please/commit/ef9b8f0) chore: readme > README (Jitendra Adhikari)
- [fb4320f](https://github.com/adhocore/please/commit/fb4320f) docs: bump info (Jitendra Adhikari)
- [3d66eb8](https://github.com/adhocore/please/commit/3d66eb8) fix(please): bump <minor> for feat if only no scope given (Jitendra Adhikari)
- [f97428a](https://github.com/adhocore/please/commit/f97428a) revert: v0.2 (Jitendra Adhikari)
- [944bd2b](https://github.com/adhocore/please/commit/944bd2b) feat(please): bump minor there is  in commit (Jitendra Adhikari)
- [b864ead](https://github.com/adhocore/please/commit/b864ead) feat(please): add commit user name [closes #8] (Jitendra Adhikari)
- [fe5b34a](https://github.com/adhocore/please/commit/fe5b34a) docs: change log (Jitendra Adhikari)

## [0.1.0] 2018-08-14 16:08:04 UTC

- [629f15a](https://github.com/adhocore/please/commit/629f15a) fix(please): CHLOG used wrong defaults
- [757694b](https://github.com/adhocore/please/commit/757694b) docs: add sample changelog
- [6450952](https://github.com/adhocore/please/commit/6450952) feat(please): changelog generation
- [4c0d950](https://github.com/adhocore/please/commit/4c0d950) refactor(please): commit log parsing
- [cd96964](https://github.com/adhocore/please/commit/cd96964) refactor(please): use gpush flag
- [4a64767](https://github.com/adhocore/please/commit/4a64767) refactor(please): reorder stuffs
- [39595fd](https://github.com/adhocore/please/commit/39595fd) feat(please): support --chlog (changelog), --chash (commit hash)
- [d0397ce](https://github.com/adhocore/please/commit/d0397ce) docs
- [61ef012](https://github.com/adhocore/please/commit/61ef012) chore: add comments, cleanup junk
- [d2c1b21](https://github.com/adhocore/please/commit/d2c1b21) docs: reorder options, add --chlog, --chash flags chlog - to create changelog.md chash - to prepend commit hash (with url) in changelog &/or release note
- [c9de526](https://github.com/adhocore/please/commit/c9de526) chore: update header
