# Cobalt-Cowboy

A RISC-V-based M17-capable radio running OpenRTX Firmware

The goal of this project is to make available a hackable radio development platform built using open-source hardware and firmware, reducing the copyright and patent overhead required to build radio equipment and technology.

The intended users of this project include licenced Amateur Radio operators and students.

This repo includes the PCB, Schematic, and associated [KiCAD](https://www.kicad.org/) project files, as well as a parts list and any information necessary to build your own Cobalt Cowboy. In essence, a ESP32C3+CC1200 evaluation board built for use with the [M17 Project](https://m17project.org/) digital data and voice protocol and capabilities of the [OpenRTX firmware](https://openrtx.org).

The OpenRTX firmware is a Zephyr RTOS built from the ground-up with digital mode radio in mind, supporting the M17 protocol. M17 protocol leverages Codec2 instead of AMBE, directly removing the necessity of DVSI hardware or navigating the licensing minefield therein. 

> * The `ESP32-C3-WROOM-02`, is a `RISC-V` single-core 32-bit microprocessor, where `RISC-V` is [RISC-V International](http://riscv.org/) IP. They allow **derivative** works and **unrestricted use** of the ISA.
> * As of late September 2023, the OpenRTX team is working on retargeting for the [T-TWR-Plus](https://www.lilygo.cc/products/t-twr-plus), a `ESP32-S3-WROOM-1-N16R8`-based UHF or VHF capable radio device. However, the restrictive licensing and black box ISA do not align with the goals of this project.

## Getting Started

1. Set up the [Zephyr](https://docs.zephyrproject.org/latest/develop/getting_started/index.html) development environment
2. Set up the [Zephyr-based target toolchain](https://openrtx.org/#/compiling?id=compiling-a-zephyr-based-target) for OpenRTX
3. Build and compile an OpenRTX image for the `ESP32-C3-WROOM-02` target.

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
* [OpenRTX](https://openrtx.org) for their radio firmware for digital ham devices