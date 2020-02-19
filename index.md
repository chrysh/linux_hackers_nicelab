# Linux Hackers Nicelab Blog

## Getting Started with OP-TEE

The [documentation](https://optee.readthedocs.io/) on how to get started with OP-TEE is actually abundant and and well written, once you know what to search for.
Find [here](https://optee.readthedocs.io/en/latest/building/devices/rpi3.html) the instructions what to compile for Raspberry Pi 3.

In order to boot a RaspberryPi 3 with OP-TEE, you need to compile five things:

* A bootloader supporting OP-TEE (see [build doc](https://optee.readthedocs.io/en/latest/building/gits/build.html#build))
* A [Linux OS](https://optee.readthedocs.io/en/latest/building/gits/optee_os.html) containing an OP-TEE kernel module
* A rootfs containing a `ta-supplicant` running in the insecure world and enabling the communication between host program and with the TA running in the secure world, which can be compiled with [OP-TEE client program](https://optee.readthedocs.io/en/latest/building/gits/optee_client.html). The client provides the libraries to compile the host program.
* An [OP-TEE host program](https://optee.readthedocs.io/en/latest/building/gits/optee_examples/optee_examples.html) running the insecure world and communication with the TA over the OP-TEE API
* An [OP-TEE Trusted Application (TA)](https://github.com/linaro-swg/optee_examples) running in the secure world

You can also find the [hello world examples](https://github.com/linaro-swg/optee_examples) repository on GitHub with TA (Trusted Application) and host program. The TAs have to be copied to `/lib/optee_armtz` in the devices rootfs and are identified by the UUID.
