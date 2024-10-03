# nimble-TWS-2024

This repository contains materials for the NIMBLE workshop at the 2024 Annual Conference of The Wildlife Society in Baltimore, Maryland, USA.

This is scheduled as a one-day workshop from 8am-5pm. The schedule will provide plenty of time for breaks and lunch.

To prepare for the workshop:

 - Install NIMBLE (see below)
 - Install additional packages (see below)
 - Download the materials provided in this repository

All materials for the workshop will be in this GitHub repository. If you're familiar with Git/GitHub, you already know how to get all the materials on your computer. If you're not, go [here](https://github.com/nimble-training/nimble-TWS-2024), click the (green) "Code" button, and choose the "Download ZIP" option.

## Background for the workshop

This workshop will focus on the `nimble` R package, not on statistical methodology per se.  The material assumes attendees have basic knowledge of ecological statistical models such as capture-recapture, occupancy, N-mixture, and hidden Markov models. (We will not use all of those!) You will still be able to follow the workshop without this background, but the workshop is geared towards participants already familiar with these topics.

## Help with NIMBLE

The NIMBLE web site is [here](https://r-nimble.org).

The NIMBLE user manual is [here](https://r-nimble.org/html_manual/cha-welcome-nimble.html).

A NIMBLE "cheatsheet" is available [here](https://r-nimble.org/documentation).

## Installing NIMBLE

NIMBLE is an R package available on CRAN, so in general it will be straightforward to install as with any R package. However, NIMBLE does require a compiler and related tools installed on your system.

The steps to install NIMBLE are:

1. Install compiler tools on your system. [https://r-nimble.org/download](https://r-nimble.org/download) will point you to more details on how to install *Rtools* on Windows and how to install the command line tools of *Xcode* on a Mac. Note that if you have packages requiring a compiler (e.g., *Rcpp*) on your computer, you should already have the compiler tools installed.

2. Install the *nimble* package from CRAN in the usual fashion of installing an R package (e.g. `install.packages("nimble")`). More details (including troubleshooting tips) can also be found in Section 4 of the [NIMBLE manual](https://r-nimble.org/html_manual/cha-installing-nimble.html).

3) Test that the installation is working, by running the following code in R:

```
library(nimble)
code <- nimbleCode({ x ~ dnorm(0, 1) })
model <- nimbleModel(code)
cModel <- compileNimble(model)
```

If the above code runs without error, you're all set. If not, please see the troubleshooting tips.  The most common problems have to do with proper installation of the compiler tools.  On Windows, the `PATH` system variable must be set (see link to Rtools installation details from our download linked above).  On Mac OSX, command line tools must be installed as part of Xcode.  If you still have problems, please email the [nimble-users group](https://r-nimble.org/more/issues-and-groups) for help.

In general, we encourage you to update to the most recent version of NIMBLE (version 1.2.1).

## Installing additional packages

Prior to the workshop, you should also install the following R packages (beyond those automatically installed with `nimble`), which can be installed as follows:

```
install.packages(c("nimbleHMC", "mcmcplots", "coda", "nimbleEcology", "compareMCMCs"))
```

