# LODEX

LODEX is an experimentation aiming to link [ISTEX](http://www.istex.fr) data to the web of data.

> **Warning**: LODEX is not funded by ISTEX.

## Start

To start `lodex`:

```bash
$ lodex /path/to/repository
```

The repository pointed can be empty.

## Settings

You can put your settings in any of these paths:

- `./.lodexrc` (or any upper level repository: `../`, `../../`, *etc*.)
- `$HOME/.lodexrc`
- `$HOME/.lodex/config`
- `$HOME/.config/lodex`
- `$HOME/.config/lodex/config`
- `/etc/lodexrc`
- `/etc/lodex/config`

Or you can pass it:

- in command line arguments,
- in variables prefixed with `lodex`,
- via an option `--config file`, then from that file.

## Use

To be able to do anything with the LODEX, you have to first *create a table*.

In order to create a table:
- [start lodex](#start),
- go to the URL given (usually http://localhost:3000/),
- click on "Back office",
- click on "Table", then "Create new one"

There should be a table, visible by clicking on "Index".

## Contribute

Here are few indicators of the quality of the code, they can be used as indications on what can be improved:

[![bitHound Overall Score](https://www.bithound.io/github/Inist-CNRS/lodex/badges/score.svg)](https://www.bithound.io/github/Inist-CNRS/lodex)
[![bitHound Dependencies](https://www.bithound.io/github/Inist-CNRS/lodex/badges/dependencies.svg)](https://www.bithound.io/github/Inist-CNRS/lodex/master/dependencies/npm)
[![bitHound Dev Dependencies](https://www.bithound.io/github/Inist-CNRS/lodex/badges/devDependencies.svg)](https://www.bithound.io/github/Inist-CNRS/lodex/master/dependencies/npm)
[![bitHound Code](https://www.bithound.io/github/Inist-CNRS/lodex/badges/code.svg)](https://www.bithound.io/github/Inist-CNRS/lodex/master/files)

To run `lodex`, use:

```bash
$ DEBUG=castor*,console* ./lodex /datas/lodex/empty/
```
