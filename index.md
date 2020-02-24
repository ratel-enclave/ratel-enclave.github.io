---
layout: default
---

## Ratel Overview

Commercial modern processors today have native support for trusted execution environments (TEEs) to run user-level applications in isolation from other software on the system. A prime example of such a TEE is Intel Software Guard eXtenstions (SGX). The hardware-isolated environment created by SGX, commonly referred to as an _enclave_, allows running a user-level application without trusting the operating system. Enclave memory is isolated from all other softwares on the system, even from the privileged OS or hypervisor. While being a promising hardware-rooted building block, enclaves have severely limited capabilities, such as no native access to system calls and standard OS abstractions. On the other hand real-world applications heavily relies upon OS primitives like system calls, dynamic libraries, multi-threading, multi-processing, signal handling etc.

We present a new system called Ratel-enclave which provides the capability to run unmodified x86-64 Linux binaries within Intel SGX enclaves. Ratel-enclave gives native applications the ability to use OS level primitives while running with Intel SGX support. Ratel-enclave uses dynamic binary translation which is a mature technique to enable cross-platform binary compatibility. Using DBT to address the binary compatibility issue has the advantage of having smaller TCB than other approaches (Eg: Using Library OS inside enclaves).

## Before we begin with Ratel-enclave

Ratel runs on Intel(R) SGX enclaves on Linux platforms. Ratel works on the x86-64 architecture and is currently tested on Ubuntu 16.04 (both server and desktop version), with Linux kernel versions 4.15.0. Before you start using Ratel, you should setup a stable Intel SDK developement environment. Then you can quickly test Ratel with applications. Please follow the instructions below, to setup Intel SGX environment and Ratel on your system.

The Linux SGX developer environment comprises of hardware with SGX support, bios support for SGX, the SGX driver, the SGX SDK, and the SGX Platform Software. Out of these, the hardware support depends on your processor and the BIOS support is provided by the vendor. The SGX driver, SDK and PSW are provided by Intel.

### Hardware support and BIOS setting

*   Check if your machine is listed in the following list of hardware which supports Intel SGX.
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

Currently we have tested Ratel with more than 6 benchmark suites such as:

```
  * Parsec-Splash-2
  * SPEC CPU
  * HBench-OS
  * IOzone
  * FSCQ File system
  * FSCQ single-system call
```
We have run following real world applications successfully with Ratel till now: 

```
  * Privado-Torch
  * Lighttpd
  * H2O
  * Memcached
  * SQLite
  * CURL
```

The related benchmarks and applications can be seen from [here](https://github.com/ratel-enclave/ratel-tests).

## Current status

Although Ratel surely is not full-featured or stable enough, we have demonstrated the effectiveness of Ratel with above mentioned benchmarks and applications. Ratel is actively being developed by Ratel Team for enabling more features, such as implementing multi-processing, bridging the Ratel client interface for DBI, supporting multi-language environment and additional functionalities required in various settings.

## Ratel Team

  * [Shweta Shinde](https://people.eecs.berkeley.edu/~shwetas/)
  * [Pinghai Yuan](https://www.comp.nus.edu.sg/~yuanping/)
  * [Jinhua Cui]
  * [Satyaki Sen](https://www.linkedin.com/in/satyaki-sen-a542a795/)
  * [Prateek Saxena](https://www.comp.nus.edu.sg/~prateeks/)
  
## Contact us

For any questions or bug reports, please feel free to write to <ratel.enclave@gmail.com> or post an issue on our GitHub repository: <https://github.com/ratel-enclave/ratel/issues>.

