# Home Assistant Add-on: Homebridge

![Supports aarch64 Architecture][aarch64-shield]
![Supports amd64 Architecture][amd64-shield]
![Supports armhf Architecture][armhf-shield]
![Supports armv7 Architecture][armv7-shield]

Run [Homebridge](https://homebridge.io) as a Home Assistant add-on to bring HomeKit support to non-native smart home devices.

## About

Homebridge is a lightweight Node.js server that emulates the iOS HomeKit API. It allows you to integrate thousands of devices that don't support HomeKit natively, using community-developed plugins.

## Features

- 🏠 Runs Homebridge with the official Web UI (port 8581)
- 🔌 Install and manage plugins directly from the Web UI
- 💾 Persistent storage — your config and plugins survive restarts
- 🌐 Host network mode for reliable mDNS/Bonjour discovery
- 🔒 Supports aarch64, amd64, armhf, and armv7

## Documentation

Full documentation is available in [DOCS.md](DOCS.md).

## Quick Start

1. Install the add-on
2. Start it
3. Open the Web UI at `http://homeassistant.local:8581`
4. Login with `admin` / `admin` and change your password
5. Pair with Apple Home using the displayed PIN

[aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[amd64-shield]: https://img.shields.io/badge/amd64-yes-green.svg
[armhf-shield]: https://img.shields.io/badge/armhf-yes-green.svg
[armv7-shield]: https://img.shields.io/badge/armv7-yes-green.svg
