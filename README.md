![rhumba header image](rhumba_header.png)

# Rhumba 🐍

¡Caramba! R bindings for micromamba!

The R package manager that is blazingly fast ⚡. Powered by [mamba](https://github.com/QuantStack/mamba/).

In early stages of development, but pretty usable.

## Installation

With either mamba or conda:

`mamba install rhumba`

`conda install rhumba`

## Use

You can use Mamba as your new package manager.

Set the channel you'd rather use:

`rhumba::set_channels(c("conda-forge", "default"))`

Try installing something:

`rhumba::install("xtensor")`

You might need to setup your `MAMBA_ROOT_PREFIX` if you've never done it before.
You can do that by calling:

`rhumba::set_root_prefix(/path/to/prefix)`

Or use  micromamba shell init ... to initialize your shell, then restart. Check 
the use of micromamba [here](https://gist.github.com/wolfv/fe1ea521979973ab1d016d95a589dcde).

## Installation from source

### Requirements:

First make sure to have the following R packages:

- Rcpp
- Devtools

And the softwares:

- autoconf
- automake
- libtool
- nlohmann_json
- cpp-filesystem
- libmamba

These can be downloaded with mamba:
`mamba install -c conda-forge r-rcpp r-devtools nlohmann_json cpp-filesystem libtool libmamba`

#### Windows, Mac and Linux:

Install packages:

```
install.packages("Rcpp")
install.packages("devtools")
```

### Setup:

Inside the R environment, first generate the bidinings required to call C++ functions from R functions adorned with `Rcpp::export`:

`Rcpp::compileAttributes()`

Then:

`devtools::install()`

And you're ready to use Rhumba!

## Testing

You can run `devtools::check()` inside your R environment as a sanity check. More information about this command's output [here](https://r-pkgs.org/r-cmd-check.html).

## License

We use a shared copyright model that enables all contributors to maintain the copyright on their contributions.

This software is licensed under the BSD-3-Clause license. See the LICENSE file for details.
