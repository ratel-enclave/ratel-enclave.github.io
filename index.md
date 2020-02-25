---
layout: default
---

## Ratel

Ratel is a new system which provides the capability to run unmodified x86-64 Linux binaries within Intel SGX enclaves. Ratel enables dynamic binary translation (DBT) inside SGX enclaves, i.e., it changes the program execution on-the-fly to be compatible with SGX abstractions. Specifically, Ratel enables [DynamoRio](https://dynamorio.org/) inside SGX enclaves. Ratel has a small trusted codebase (about 20KLOC) inside the enclave and has the potential to enable cross-platform binary compatibility.

## Before we begin with Ratel

Ratel runs on Intel(R) SGX enclaves on Linux platforms. Ratel works on the x86-64 architecture and is currently tested on Ubuntu 16.04 (both server and desktop version), with Linux kernel versions 4.15.0. Before you start using Ratel, you should setup a stable Intel SDK developement environment. Then you can quickly test Ratel with applications. Please follow the instructions below, to setup Intel SGX environment and Ratel on your system.

The Linux SGX developer environment comprises of hardware with SGX support, bios support for SGX, the SGX driver, the SGX SDK, and the SGX Platform Software. Out of these, the hardware support depends on your processor and the BIOS support is provided by the vendor. The SGX driver, SDK and PSW are provided by Intel.

### Hardware support and BIOS setting

*   List of hardwares which supports Intel SGX.
    [SGX supported hardware](https://github.com/ayeks/SGX-hardware).
*   Ensure that you have enabled SGX support in your BIOS.
*   Run the test-sgx.c code from https://github.com/ayeks/SGX-hardware to quickly check if SGX is available for your CPU and enabled in BIOS.

### Software Requirements

One of the following operating systems should be installed on your machine.

*   [Ubuntu* Desktop-16.04-LTS 64bits](http://old-releases.ubuntu.com/releases/16.04.1/ubuntu-16.04.1-desktop-amd64.iso).
*   [Ubuntu* Server-16.04-LTS 64bits](http://old-releases.ubuntu.com/releases/16.04.1/ubuntu-16.04.1-server-amd64.iso).


## Installation and usage

1.  **Build and install Intel SGX driver, modified SDK, modified PSW**

    <https://github.com/ratel-enclave/ratel#building-with-intelr-sgx-dependencies>

2.  **Build and install Ratel**

    <https://github.com/ratel-enclave/ratel#building-and-setting-ratel-sgx>

3.  **Run Ratel with applications**

    <https://github.com/ratel-enclave/ratel#how-to-run-an-application-with-ratel>

## Benchmarks and applications

Currently we have tested Ratel with 6 benchmark suites :

```
  * Parsec-Splash-2
  * SPEC CPU
  * HBench-OS
  * IOzone
  * FSCQ File system
  * FSCQ single-system call
```
We have run following real world applications successfully with Ratel : 

```
  * Privado-Torch
  * Lighttpd
  * H2O
  * Memcached
  * SQLite
  * CURL
```

The related benchmarks and applications can be accessed from [here](https://github.com/ratel-enclave/ratel-tests).

## Current status

Ratel is under active development and a research prototype at this stage. Please use at your own risk. 
Please check out the list of benchmarks / applications we have successfully tested thus far.
We invite contributions from the community and have a long wish list of features and stability improvements. Please contact us (see below) if you wish to talk to us.

Features included in this prototype release : support for program loading, 220 Linux system calls, basic syscall error-handling, multi-threading, signals, and mutex synchronization primitives.

## Ratel Team

We are researchers from NUS and UC Berekely:

  * [Shweta Shinde](https://people.eecs.berkeley.edu/~shwetas/)
  * [Pinghai Yuan](https://www.comp.nus.edu.sg/~yuanping/)
  * [Jinhua Cui]
  * [Satyaki Sen](https://www.linkedin.com/in/satyaki-sen-a542a795/)
  * [Prateek Saxena](https://www.comp.nus.edu.sg/~prateeks/)
  
## Contact us

For any questions or bug reports, please feel free to write to <ratel.enclave@gmail.com> or post an issue on our GitHub repository: <https://github.com/ratel-enclave/ratel/issues>.

### Industry Partners

* [Anqlave](https://www.anqlave.co)
