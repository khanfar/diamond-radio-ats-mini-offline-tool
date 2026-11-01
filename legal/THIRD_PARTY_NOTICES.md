# Diamond Radio ATS Mini Offline Tool — third-party notices

This release contains the Diamond Radio ATS Mini Offline Tool and Diamond Dual
Boot v2.0 images. It does not contain receiver firmware, receiver decoders, or
the GNBD/miniradio receiver application. Diamond-specific application source is
private and the Windows application is distributed as freeware; see
`DIAMOND_FREEWARE_NOTICE.txt`.

`LICENSE` preserves the upstream GNBD/miniradio MIT notice supplied with the
Diamond receiver project. It is retained for attribution continuity when users
maintain those receiver installations; it does not claim that this maintenance
tool contains receiver code or replace any Diamond or third-party terms.

## Diamond Dual Boot v2.0

- DiamondMiniBoot, its partition layout and its ESP-IDF bootloader patch:
  Copyright (c) 2026 Diamond Radio (MKhanfar), MIT License. Full text:
  `DIAMOND-BOOT-MIT.txt`.
- LovyanGFX 1.2.30: lovyan03, FreeBSD two-condition license. Its license also
  preserves the Adafruit_GFX, Adafruit_ILI9341 and TFT_eSPI notices. Full text:
  `THIRD_PARTY_LICENSES/LOVYANGFX.txt`.
- Arduino-ESP32 2.0.17: Espressif Systems and contributors, LGPL-2.1-or-later.
  The unmodified official framework is used to build the boot manager. License:
  `THIRD_PARTY_LICENSES/ARDUINO-ESP32-LGPL-2.1.txt`. Upstream source:
  https://github.com/espressif/arduino-esp32/tree/2.0.17
- ESP-IDF 5.5.5 and linked framework components, including the second-stage
  bootloaders: Espressif Systems and respective contributors. Apache License
  2.0 and accompanying component notices are in `THIRD_PARTY_LICENSES/`.

## Offline Windows maintenance application

- espflash 4.7.0: esp-rs contributors, MIT OR Apache-2.0. The separate
  executable is invoked by the application; its license choices are supplied as
  `ESPFLASH-MIT.txt` and `ESPFLASH-APACHE-2.0.txt`.
- Python 3.13 runtime: Python Software Foundation License Version 2 and the
  additional notices in `PYTHON-LICENSE.txt`.
- PySerial 3.5: Chris Liechti and contributors, BSD three-condition license;
  full text in `PYSERIAL-LICENSE.txt`.
- Tcl/Tk: Regents of the University of California, Sun Microsystems,
  Scriptics, ActiveState, Apple and other contributors; see `TK-LICENSE.txt`.
- PyInstaller Windows bootloader: PyInstaller Development Team and earlier
  contributors. The unmodified bootloader is used under its explicit bootloader
  exception; run-time hooks are Apache-2.0. See `PYINSTALLER-LICENSE.txt`.
  This does not apply GPL terms to the Diamond application.

Third-party components remain under their own licenses. No upstream copyright
or permission notice is replaced by Diamond branding or distribution terms.
