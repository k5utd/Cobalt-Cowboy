# Cobalt-Cowboy

A RISC-V-based digital mode radio running OpenRTX Radio Firmware

The goal of this project is to make available a hackable radio development platform for evaluating radio transceivers and experimenting with amateur multi-mode radio technology.

The intended users of this project include licenced Amateur Radio operators and students.

> [!NOTE]
> This repository includes the PCB, Schematic, and associated [KiCAD](https://www.kicad.org/) project files, as well as a parts list and any information necessary to build your own Cobalt Cowboy.

## Background

### OpenRTX Real-Time Operating Systems

This project intends to leverage the growing RF vendor support of Zephyr Project [ZephyrRTOS](https://zephyrproject.org/learn-about/).

The [OpenRTX firmware](https://openrtx.org) is an RTOS-agnostic application built from the ground-up with digital mode radios (DMR) in mind, some of which support the M17 protocol with hardware modification after firmware flashing.

The OpenRTX firmware typically uses the [Miosix](https://miosix.org/) kernel, primarily supporting STM32 targets on the ARM Cortex-M4F architecture, and is being ported to ZephyrRTOS to take advantage of support for more architectures.

### M17 Digital Mode and Codec2

For the purposes of this project, having multiple vocoder options to choose from for digital mode operation is desirable for reducing vendor lockin and avoiding product obsolescence.

The [M17 Project](https://m17project.org/) M17 RF protocol is an open protocol specification that leverages [Codec2](https://en.wikipedia.org/wiki/Codec_2) instead of DVSI [AMBE](https://en.wikipedia.org/wiki/Multi-Band_Excitation). 

Codec2 allows for open implementations as a software-defined vocoding alternative to DVSI vocoding hardware, complimenting the open communication stack of M17.

### Limitations and Alternatives 

The LILYGO [T-TWR Plus](https://www.lilygo.cc/products/t-twr-rev2-1) is a development board for evaluating the `NiceRF SA868` Walkie Talkie and `Quectel L76K` GNSS modules. The T-TWR Plus is as of September 2023 what motivated the OpenRTX team to begin porting OpenRTX to ZephyrRTOS. As of July 2024, rev2.1 now shows promise for experimenting with software-defined digital mode radio on VHF or UHF with improved RF module interfacing.

LILYGO has maintains a [repository](https://github.com/Xinyuan-LilyGO/T-TWR) of example testing firmware and schematics, However, the T-TWR Plus is not necessarily open source hardware, being schematic-available with no manufacturing files. NiceRF does not maintain public factory firmware of the SA868 either, so OpenRTX [sa8x8-fw](https://github.com/OpenRTX/sa8x8-fw) is necessary for use with OpenRTX.

## Getting Started

> [!IMPORTANT]
> This repository is primarily the hardware, the firmware and instructions are to be made available upstream OpenRTX.

### Board Fabrication

The board stackup is intended for OSHPark fabrication services.

The main board features an Espressif `ESP32-C3` and integrates the Texas Instruments `CC1200` Sub-Ghz transceiver. Most components are surface mount, and can get as small as `0602`.

### Firmware 
1. Set up the [Zephyr](https://docs.zephyrproject.org/latest/develop/getting_started/index.html) development environment
2. Set up the [Zephyr-based target toolchain](https://openrtx.org/#/compiling?id=compiling-a-zephyr-based-target) for OpenRTX
3. TODO: Build and compile an OpenRTX image for the `cobalt-cowboy` target

## Contact

To reach out, please join the Discord server.

[![](https://dcbadge.vercel.app/api/server/H3aeqqR5t6?style=flat)](https://discord.gg/H3aeqqR5t6)

CO: [Eric Mutton](https://github.com/ericmutton), username `cyndre`.

## License

This project is released under the GNU GPL v3.

See [LICENSE](LICENSE)

## Credits

Our thanks go to the following organizations for their efforts and advice:
* [M17 Project](https://m17project.org/) for their digital radio protocol for data and voice
* [OpenRTX](https://openrtx.org) for their radio firmware for digital mode radios and ham devices
