# dispRity
[![Build Status](https://travis-ci.org/TGuillerme/dispRity.svg?branch=release)](https://travis-ci.org/TGuillerme/dispRity)
[![DOI](https://zenodo.org/badge/doi/10.5281/zenodo.31742.svg)](http://dx.doi.org/10.5281/zenodo.31742)

**dispRity** is a `R` package for summarising ordinated matrices (e.g. MDS, PCA, PCO or PCoA analysis).

## Installing dispRity
```r
if(!require(devtools)) install.packages("devtools")
install_github("TGuillerme/dispRity", ref = "release")
library(dispRity)
```
The following installs the latest released version (see patch notes below). For the piping hot development version (not recommended), replace the `ref="release"` option by `ref="master"`. If you're using the `master` branch, see the latest developement in the [patch note](https://github.com/TGuillerme/dispRity/blob/master/patch_notes.md).

#### WARNING: There might be some conflicting versions with R 3.2.3
When loading/installing the `paleotree` package that depends on `phytools` and `phangorn` you might get an issue with `Biostrings` dependencies (see [this issue for details](https://github.com/hadley/devtools/issues/700)). This problem can be solved by installing it manually:
```r
source("http://bioconductor.org/biocLite.R")
biocLite("Biostrings")
```
Or by using the latest version (`0.2`) of the `dispRity` package:
```r
install_github("TGuillerme/dispRity", ref = "master")
```
Note however that the new functionalities in this [future version](https://github.com/TGuillerme/dispRity/blob/master/patch_notes.md) (`0.2`) are not all properly tested yet and may contain errors. All the former functionalities still work fine as in the `0.1.2` release!


#### Vignettes
*  The package manual [here (in .Rnw)](https://github.com/TGuillerme/dispRity/blob/master/doc/dispRity-manual.Rnw) or [here (in .pdf)](https://github.com/TGuillerme/dispRity/blob/master/doc/dispRity-manual.pdf).
*  A tutorial for palaeobiologists [here (in .Rnw)](https://github.com/TGuillerme/dispRity/blob/master/doc/dispRity-palaeo-demo.Rnw) or [here (in .pdf)](https://github.com/TGuillerme/dispRity/blob/master/doc/dispRity-palaeo-demo.pdf).
*  A tutorial ecologists [here (in .Rnw)](https://github.com/TGuillerme/dispRity/blob/master/doc/dispRity-ecology-demo.Rnw) or [here (in .pdf)](https://github.com/TGuillerme/dispRity/blob/master/doc/dispRity-ecology-demo.pdf).
*  The disparity metrics [here (in .Rnw)](https://github.com/TGuillerme/dispRity/blob/master/doc/dispRity-metrics.Rnw) or [here (in .pdf)](https://github.com/TGuillerme/dispRity/blob/master/doc/dispRity-metrics.pdf).

##### Patch notes
* 2015/12/01 - v0.1.2
  * new function: `get.dispRity` for subsampling dispRity objects
  * new function: `extract.dispRity` for extracting disparity results
  * new function: `test.dispRity` for applying tests to `dispRity` objects
  * new function: `make.metric` for helping creating your very own disparity metric
  * new metric: `hyper.volume` for measuring the morphospace hyper-ellipsoid volume
  * `metric` argument from `dispRity` can now intake up two three functions (see `dispRity.metric` and `make.metric`)
  * many improved functions manuals and examples!
  * improved vignettes:
    * *dispRity palaeo demo* a quick demo aimed more for palaeobiologist
    * *dispRity ecology demo* a quick demo aimed more for ecologists
    * *dispRity manual* for people that want to know the package in details
    * *dispRity metrics* for explaining how the disparity metric implementation works
  
Previous patch notes and the *next version* ones can be seen [here](https://github.com/TGuillerme/dispRity/blob/master/patch_notes.md).

#### Implemented metric
A list of implemented metrics (or soon to be implemented) is available [here](https://github.com/TGuillerme/dispRity/blob/master/metrics.md).

Authors
-------
[Thomas Guillerme](http://tguillerme.github.io)


Citation
-------
If you are using this package, please cite the following Zenodo DOI (an associated paper will be added soon):

* Guillerme, T. (**2015**). dispRity: a package for measuring disparity in R. Zenodo. 10.5281/zenodo.31742

[BibTeX](https://zenodo.org/record/31742/export/hx), [EndNote](https://zenodo.org/record/31742/export/xe), [DataCite](https://zenodo.org/record/31742/export/dcite3), [RefWorks](https://zenodo.org/record/31742/export/xw)
