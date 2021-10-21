---
layout: default
---

## Ratel

Ratel is a new framework which enables dynamic binary translation on Intel SGX. Ratel offers ***complete interposition***, the ability to interpose on all executed instructions in the enclave and monitor all interactions with the OS. Ratel demonstrates its effectiveness by both building a binary compatibility layer for
Linux legacy applications and enabling instrumentation options for monitoring runtime code behaviors. Specifically, Ratel enables [DynamoRIO](https://dynamorio.org/) inside SGX enclaves. Ratel achieves better binary compatibility and has a comparable trusted codebase in the enclave. Further, Ratel is able to serve as a general foundation for implementing a large variety of inline security monitors to safeguard enclaves from bugs and from the untrusted OS.

## Before we begin with Ratel

Ratel runs on Intel<sup>®</sup> SGX enclaves on Linux platforms. Ratel works on the x86-64 architecture and is currently tested on Ubuntu 16.04 (both server and desktop version), with Linux kernel versions 4.15.0. Before you start using Ratel, you should setup a stable Intel SDK developement environment. Then you can quickly test Ratel with applications. Please follow the instructions below, to setup Intel SGX environment and Ratel on your system.

The Linux SGX developer environment comprises of hardware with SGX support, bios support for SGX, the SGX driver, the SGX SDK, and the SGX Platform Software. Out of these, the hardware support depends on your processor and the BIOS support is provided by the vendor. The SGX driver, SDK and PSW are provided by Intel.

### Hardware support and BIOS setting

*   [SGX supported hardware](https://github.com/ayeks/SGX-hardware).
*   Ensure that you have enabled SGX support in your BIOS.
*   Run the test-sgx.c code from [here](https://github.com/ayeks/SGX-hardware) to quickly check if SGX is available for your CPU and enabled in BIOS.

### Software Requirements

One of the following operating systems should be installed on your machine.

*   [Ubuntu* Desktop-16.04-LTS 64bits](http://old-releases.ubuntu.com/releases/16.04.1/ubuntu-16.04.1-desktop-amd64.iso).
*   [Ubuntu* Server-16.04-LTS 64bits](http://old-releases.ubuntu.com/releases/16.04.1/ubuntu-16.04.1-server-amd64.iso).

## Installation and usage

1.  **Build and install Intel SGX driver, modified SDK, modified PSW, Ratel with the auto installation script**
      
      <https://github.com/ratel-enclave/ratel#building-intelr-sgx-dependencies-and-ratel-with-auto-installation-script>

2.  **Manually Build and install Intel SGX driver, modified SDK, modified PSW**

    <https://github.com/ratel-enclave/ratel#building-with-intelr-sgx-dependencies>

3.  **Manually Build and install Ratel**

    <https://github.com/ratel-enclave/ratel#building-and-setting-ratel-sgx>

4.  **Run Ratel with applications**

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
  * 138 Linux utilities
```
Two interpreters like Python and R languages tested :
```
  * R
  * Python 2
  * Python 3
```

The related benchmarks, applications and runtimes can be accessed from [here](https://github.com/ratel-enclave/ratel-tests).

## Current status

Ratel is under active development and a research prototype at this stage. Please use at your own risk. 
Please check out the list of benchmarks / applications we have successfully tested this far.
We invite contributions from the community and have a long wish list of features and stability improvements. Please contact us (see below) if you wish to talk to us.

Features included in this prototype release : support for program loading, around 220 Linux system calls, basic syscall error-handling, memory management, multi-threading, signals, and synchronization primitives.

## Ratel Team

We are researchers from NUS, ETH and NUDT:

  * [Jinhua Cui](https://cimcs.github.io/)
  * [Pinghai Yuan](https://dblp.org/pid/153/3110.html)
  * [Satyaki Sen](https://www.linkedin.com/in/satyaki-sen-a542a795/)
  * [Shweta Shinde](https://n.ethz.ch/~sshivaji/)
  * [Prateek Saxena](https://www.comp.nus.edu.sg/~prateeks/)
  
## Contact us

For any questions or bug reports, please feel free to write to <ratel.enclave@gmail.com> or post an issue on our GitHub repository: <https://github.com/ratel-enclave/ratel/issues>.

### Industry Partners

* [Anqlave](https://www.anqlave.co)
