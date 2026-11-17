# EdgeSense

Embedded IoT platform for predictive maintenance of industrial rotating machines: STM32 sensor node, ESP32 wireless bridge and an embedded Linux gateway.

> Status: work in progress. Milestone J0 (environment, toolchain, base firmware) is done.

## Goal

Detect an anomaly on an industrial machine before it fails, by measuring vibration, temperature and current, analyzing the signal on the microcontroller and raising alerts through a dashboard.

## Hardware

- ST NUCLEO-L4R5ZI (STM32L4R5ZI, Cortex-M4F)
- Espressif ESP32-DevKitC V4
- Embedded Linux gateway (Buildroot, then Yocto, run under QEMU)

## Repository layout

    firmware/stm32-node/   STM32 firmware (CMake, STM32Cube HAL)
    docs/                  Design documents

## Build the STM32 firmware

Requirements: gcc-arm-none-eabi, cmake, ninja-build (tested on Ubuntu 24.04).

    cd firmware/stm32-node
    cmake --preset Debug
    cmake --build --preset Debug

## Roadmap

- [x] J0: environment and base firmware (LED blink)
- [ ] J1: sensor acquisition with FreeRTOS, frame protocol
- [ ] J2: ESP32 bridge (Wi-Fi, MQTT)
- [ ] J3: embedded Linux gateway
- [ ] J4: dashboard and alerts
- [ ] J5: vibration analysis and anomaly detection
- [ ] CI/CD pipeline (Azure DevOps)
