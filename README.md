[![Build Status](https://travis-ci.org/TGuillerme/dispRity.svg?branch=release)](https://travis-ci.org/TGuillerme/dispRity)
[![codecov](https://codecov.io/gh/TGuillerme/dispRity/branch/release/graph/badge.svg)](https://codecov.io/gh/TGuillerme/dispRity)
[![Project Status: Active - The project has reached a stable, usable state and is being actively developed.](http://www.repostatus.org/badges/latest/active.svg)](http://www.repostatus.org/#active)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.846254.svg)](https://doi.org/10.5281/zenodo.846254)

**dispRity** is a `R` modular package for measuring disparity from multidimensional matrices.

<a href="https://figshare.com/articles/New_approaches_to_disparity-through-time_analysis/3437546"><img src="http://tguillerme.github.io/images/logo-FS.png" height="15" widht="15"/></a> 
Check out the [presentation](https://figshare.com/articles/New_approaches_to_disparity-through-time_analysis/3437546) or the [video](https://www.youtube.com/watch?v=ZzipKw8W8KQ) of some of the package's novel features.

## Installing dispRity
```r
if(!require(devtools)) install.packages("devtools")
library(devtools)
install_github("TGuillerme/dispRity", ref = "release")
library(dispRity)
```

The following installs the latest release of dispRity (see patch notes below). For the piping hot development version (not recommended), replace the `ref = "release"` option with `ref = "master"`.
If you're using the `master` branch, see the [patch notes](https://github.com/TGuillerme/dispRity/blob/master/patch_notes.md) for the latest developments.

> Installation problems? Make sure you're using the latest R version (or at least `> 4.0`) and try again.

#### Vignettes

See the package manual online [here](https://rawgit.com/TGuillerme/dispRity/master/inst/gitbook/_book/index.html) or download the pdf version [here](https://github.com/TGuillerme/dispRity/raw/master/inst/gitbook/_book/dispRity_manual.pdf).

Additionally, you can learn more about the structure of `dispRity` objects [here](https://github.com/TGuillerme/dispRity/blob/master/disparity_object.md).

##### Patch notes
* 2017/08/21 - v0.4.0 *user friendly*
  * Entirely rewritten manual (in GitBook)!
  * **Removed** `hyper.volume` metric for dependencies reasons
  * **Removed** `parallel` option from `boot.matrix` (the new architecture is already super fast: >2sec for 5k taxa and 10k bootstraps!)
  * *New* function: `Claddis.ordination` and `geomorph.ordination` for automatically ordinating data from `Claddis` and `geomorph` packages!
  * *New* function: `char.diff` for calculating character differences and associated plot function (`plot.char.diff`)
  * *New* utility function: `merge.subsamples` for... merging subsamples!
  * *New* utility function: `size.subsamples` for... getting the size of subsamples in a disparity object!
  * *New* wrapping functions: `dispRity.through.time` and `dispRity.per.group` now runs easy default disparity analysis.
  * Input ordinated matrices do not need to be of maximum size `n*(n-1)`. Bigger matrices now only trigger a warning.
  * **Changed name**: `series` as a part of `dispRity` objects is now changed to `subsamples` throughout the whole package.
  * **Changed name**: `time.series` is now renamed `time.subsamples`, if dates are provided and method is `discrete`, this function doesn't need a phylogeny any more.
  * **Changed name**: `get.subsamples.dispRity` is now renamed `get.subsamples`.
  * **Modified function**: `cust.series` is now renamed `custom.subsamples` (to avoid confusion with `custard.subsamples`!). Its `factor` argument as been changed to `groups` and can now take a simple list.
  * Added `dimensions` optional argument to `dispRity` to overwrite the number of dimensions generated by `boot.matrix`.
  * `variances`, `ranges` and `centroids` are now simplified for speed. The optional arguments for data cleaning are now passed to `make.metric`.
  * `space.maker` now allows to approximate the dimensions variance distribution with the `scree` option.
 
Previous patch notes and notes for the *next version* can be seen [here](https://github.com/TGuillerme/dispRity/blob/master/patch_notes.md).

Authors
-------

* [Thomas Guillerme](http://tguillerme.github.io)
* [Natalie Cooper](http://nhcooper123.github.io)
* [Mark Puttick](https://puttickbiology.wordpress.com/)

Citation
-------
If you are using this package, please cite the following Zenodo DOI (an associated paper will be added soon):

* Guillerme, T. (**2016**). dispRity: a package for measuring disparity in R. Zenodo. 10.5281/zenodo.55646

 [BibTeX](https://zenodo.org/record/55646/export/hx), [EndNote](https://zenodo.org/record/55646/export/xe), [DataCite](https://zenodo.org/record/55646/export/dcite3), [RefWorks](https://zenodo.org/record/55646/export/xw)

Acknowledgments
-------
Some ideas/functionalities/implementations in this package where implemented following the suggestions of [Natalie Cooper](http://nhcooper123.github.io/), [Graeme Lloyd](http://www.graemetlloyd.com/), [Dave Bapst](https://github.com/dwbapst/), [Andrew Jackson](http://www.tcd.ie/Zoology/research/research/theoretical/andrewjackson.php) and [Martin Brazeau](http://www.imperial.ac.uk/people/m.brazeau).
