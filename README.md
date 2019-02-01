# NSO Installation Guide

This document provides instructions on getting started with Network Services Orchestrator.  


## Requirements

NSO can be installed on a Mac, or Linux. The additional requirements are:

* Java
* Ant

## Downloads

This evaluation copy has been provided under the terms of the Cisco
NSO Evaluation License. There are two versions of the NSO installer:

for MacOS and Linux systems respectively:

1. [NSO 4.7 Darwin](http://cs.co/nso-mac)

2. [NSO 4.7 Linux](http://cs.co/nso-linux)


## Installation


### Unpack the NSO Installer, verify digital signature.

The NSO installation is delivered with a cryptographic signature to make it possible to verify that the installation has not been altered or corrupted. This can be guaranteed since the signature was created by using a combination of cryptographic hash and public key
encryption.

Unpacking the NSO installer is performed by executing the downloaded distribution using a command like: `sh nso-VERSION.OS.ARCH.signed.bin`


The variables in the command VERSION refers to the NSO version to install, OS refers to the Operating System (linux for any Linux distribution and darwin for OS X) and ARCH refers to the CPU
architecture (x86_64). For Example:

```
$ sh nso-4.7.linux.x86_64.signed.bin
```


#### What's Included

Once NSO is unpacked, all the files are unpacked in the current directory.

1. The NSO installer nso-VERSION.OS.ARCH.installer.bin
2.  Signature generated for the NSO image nso-VERSION.OS.ARCH.installer.bin.signature
3. An enclosed Cisco signed tailf.cer x.509 end-entity certificate
containing public key that is used to verify the signature.
4. README.signature file which briefs you more details on the unpacked content and the steps on "How to run the signature verification
program". If you would like to manually verify the signature, please
refer to the steps in this file.
5. cisco_x509_verify_release.py python program that can be used to verify the 3-tier x.509 certificate chain and signature.

#### Installing NSO

Local Install of NSO Software is performed in a single user specified directory, for example in your home directory $HOME. It is always recommended to install NSO in a directory named as the version of the release. This command might look something like this. `$ sh nso-VERSION.OS.ARCH.installer.bin $HOME/ncs-VERSION --local-install`

The variables in the command VERSION refers to the NSO version to
install, OS refers to the Operating System (linux for any Linux
distribution and darwin for OS X) and ARCH refers to the CPU
architecture (x86_64). The --local-install parameter is an optional
parameter. For Example:

```
$ sh nso-4.7.linux.x86_64.installer.bin $HOME/nso-4.7
```


The installation program creates a shell script file named `ncsrc` in each NSO installation, which sets the environment variables. `source` this file to get these settings in your shell. You may want to add this sourcing command to your login sequence, such as `.bashrc`.  For csh/tcsh users there is a `ncsrc.tcsh` file using csh/tcsh syntax. The
example below assumes that you are using bash, other versions of
/bin/sh may require that you use . instead of source.


```
 $ source $HOME/ncs-4.7/ncsrc
```

## GETTING STARTED

We recommend that you start with the Getting Started guide in the doc
directory `$HOME/ncs-VERSION/doc/pdf/nso_getting_started-VERSION.pdf`

There is a lot of examples in the `$HOME/ncs-VERSION/examples.ncs`
directory. Each example has a `README` file that explains how to run it.

## Still Need help?

There is a lot of material on the [NSO Developer Hub](https://community.cisco.com/t5/nso-developer-hub/ct-p/5672j-dev-nso)

This is also where you can ask questions about anything NSO-related.
