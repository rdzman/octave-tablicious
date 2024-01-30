# Tablicious for GNU Octave

Tablicious provides tabular/relational data structures for Octave. You can think of it as "pandas for Octave".

| WARNING: This library is currently beta quality. Please do not use it in any production or business code! Seriously!! |
| ---- |

This package attempts to provide a set of mostly-Matlab-compatible implementations of the table class and related structures and functions.
It provides:

* `table` and related construction/conversion functions
* Missing Data support
  * `ismissing` and friends: `rmmissing`, `standardizeMissing`
  * `@missing`
  * `fillmissing` is not implemented yet, because that requires some actual math.
* `eqn` and `isnanny`
  * These are experimental Octave extensions for dealing with NaN-like values. They are used by `table`, `ismissing`, and friends, but should be generally useful, and need to be global so they can be overridden by user-defined classes.
* `string`
* `categorical`

It currently does not provide, but we would like to add:

* `timetable`
* Table I/O, such as `readtable`, `writetable`, and `csvread`/`dlmread` `table` support

The `string` and `categorical` support are incomplete, and less mature than the rest of the package.

## Installation and usage

### Requirements

Tablicious 0.4.x requires Octave 7.0 or newer. It may well work on earlier versions, but is not tested against them.

Tablicious does not require the Octave Forge [Statistics package](https://gnu-octave.github.io/packages/statistics/), but you will probably want it, because Statistics supplies functions that are frequently useful for data analysis in a tabular context. In particular, `ismissing()` is very useful, and the Statistics package supplies the general implementation of it.

### Quick start

To get started using or testing this project, install it using Octave's `pkg` function:

```octave
pkg install https://github.com/apjanke/octave-tablicious/releases/download/v0.3.7/tablicious-0.3.7.tar.gz
pkg load tablicious
```

### Installation for development

If you want to hack on the Tablicious code itself, set it up like this:

* Clone the repo
  * `git clone https://github.com/apjanke/octave-tablicious`
* Add the `inst/` directory from the cloned repo to your Octave path with `addpath`.

That should get everything working except for time zone conversions inside `datetime`, which require a compiled oct-file. See the developer doco in the repo for that.

## Documentation

Once you have Tablicious installed, the user manual will show up in the Octave GUI’s documentation browser.
You can also run `help <foo>` or `doc <foo>` for any of the classes or functions in Tablicious.

The documentation for Tablicious can be viewed online at <https://apjanke.github.io/octave-tablicious>. That site has the [Tablicious User Guide](https://apjanke.github.io/octave-tablicious/release/v0.3.7/user-guide/html/index.html) containing the API reference, plus some additional general and developer-oriented documentation, and alternate formats of the User Guide. See the [main doco page there](https://apjanke.github.io/octave-tablicious) for details.

Developers, especially see the [Developer Notes](https://apjanke.github.io/octave-tablicious/Developer-Notes.html) and [Design and Justification](https://apjanke.github.io/octave-tablicious/Design-and-Justification.html) pages there, which discuss how and why this library is written. There's a [TODO page](https://apjanke.github.io/octave-tablicious/TODO.html) that lists what might be coming. Also see [CONTRIBUTING](CONTRIBUTING.md) if you would like to contribute to this project.

Within this repo, you can see all that in the `docs/` directory for notes on this project. It's a local copy of the GitHub Pages site.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for more details.

### No Matlab Usage

To avoid issues with the Matlab license's Non-Compete clause, this project needs to be developed entirely using Octave, and not using Matlab at all, including for testing or benchmarking purposes. Please do not submit any Matlab test or benchmark results, or any code produced using Matlab. And if you know anything about how the Matlab internals work, please do not tell me!

## Author and Acknowledgments

Tablicious is created by [Andrew Janke](https://apjanke.net).

Thanks to [Polkadot Stingray](https://polkadotstingray-official.jimdo.com/) for [powering](https://www.youtube.com/watch?v=3ad4NsEy1tg) [my](https://www.youtube.com/watch?v=-zlq6eMycLA) [coding](https://www.youtube.com/watch?v=1z4RosaB-UQ) [sessions](https://www.youtube.com/watch?v=p6oVXuLsbxM).

Shout out to [Mike Miller](https://mtmxr.com/) for showing me how to properly structure an Octave package repo, and encouraging me to contribute.

Thanks to [Sebastian Schöps](https://github.com/schoeps) for getting me more involved in Octave development in the first place, via his [Octave.app](https://octave-app.org) project.
