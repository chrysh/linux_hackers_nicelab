# Linux Hackers Nicelab Blog

## Getting Started with OP-TEE

The [documentation on how to get started with OP-TEE](https://optee.readthedocs.io/) is actually abundant and and well written, once you know what to search for.
Find [here the instructions what to compile for Raspberry Pi 3](https://optee.readthedocs.io/en/latest/building/devices/rpi3.html).

In order to boot a RaspberryPi 3 with OP-TEE, you need to compile five things:

* A bootloader supporting OP-TEE (see [https://optee.readthedocs.io/en/latest/building/gits/build.html#build])
* An [Linux OS](https://optee.readthedocs.io/en/latest/building/gits/optee_os.html) containing an OP-TEE kernel module
* A rootfs containing a ta-supplicant, which can be compiled with [OP-TEE client program](https://optee.readthedocs.io/en/latest/building/gits/optee_client.html) running in the insecure world, which connects the user application with the trusted world. The client provides the libraries to compile the host program
* An [OP-TEE host program](https://optee.readthedocs.io/en/latest/building/gits/optee_examples/optee_examples.html) running the insecure world and communication with the TA over the OP-TEE API
* An [OP-TEE Trusted Application (TA)](https://github.com/linaro-swg/optee_examples) running in the secure world

You can also find the [hello world examples repository on GitHub](https://github.com/linaro-swg/optee_examples) with TA (Trusted Application) and host program. The TAs have to be copied to `/lib/optee_armtz` in the devices rootfs.
