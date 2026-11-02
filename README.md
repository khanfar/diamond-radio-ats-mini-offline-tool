# Diamond Radio ATS Mini Offline Tool

Official standalone Windows maintenance tool for ESP32-S3 ATS Mini radios with **8 MB or 16 MB flash**.

- Product and Diamond-specific modifications: **M Khanfar**
- Distribution: **freeware**; Diamond-specific source code is not distributed
- Official website: **[diamondradio.web.app/atsmini.html](https://diamondradio.web.app/atsmini.html)**
- Current offline-tool release: **v1.1.1**
- Bundled boot manager: **Diamond Dual Boot v2.1**

This repository contains release information, binary downloads, checksums, and legal notices only. It is not a source-code repository.

## Download

Open **[Releases](https://github.com/khanfar/diamond-radio-ats-mini-offline-tool/releases/latest)** and download `DiamondRadio-MiniTool-v1.1.1-Windows.zip`. Extract the whole ZIP, then run `DiamondRadio-MiniTool.exe`. No Python installation, account, or internet connection is required for maintenance operations.

The standalone EXE, both full Dual Boot images, and `SHA256SUMS` are also available as separate release assets. Verify downloads against the published SHA-256 checksums.

## Included functions

- Detect the ESP32-S3, COM port, and actual 8 MB or 16 MB flash capacity.
- Back up and restore the complete flash.
- Install the bundled Diamond Dual Boot v2.1 or a manually selected full Dual Boot image.
- Install firmware directly into Slot A or Slot B.
- Extract the active OTA application from a full backup, with an optional manual A/B source selector.
- Carry compatible settings and files when installing an application from a full backup.
- Erase one slot, reset the radio, or perform a guarded full-flash erase.
- Show live operation logs, elapsed time, progress, and post-write MD5 verification.

## Important backup and OTA behavior

A full backup includes the complete flash: Dual Boot when present, both application slots, settings, files, and boot-selection data. Full Restore returns the radio to that exact state. Restoring a backup made before Dual Boot removes Dual Boot; restoring a backup that already contains it restores the complete dual-boot setup.

When installing an application **from a full backup into one slot**, the tool selects the application that was active during the backup. If two valid applications are present, use **Firmware inside backup** to choose source Slot A or B explicitly. This avoids accidentally extracting an older OTA image.

You can rewrite an occupied slot directly without erasing it first. Only use **Erase Slot** when you deliberately want an empty slot or need to clear a corrupted installation.

**Slot-preserving OTA:** Dual Boot v2.1 adds an **OTA UPDATE** menu for Diamond Radio and **PUBLIC ATS MINI - SAFE OTA**. Choose the destination slot; the manager shows the release version, downloads and verifies the official release, and checks that the other slot stayed unchanged. Diamond Radio v1.0.2 and newer uses this same path from its Settings update screen. **SETTINGS → WIFI SETUP** scans networks and saves a manager-owned connection, so OTA also works into empty slots after a clean install. Typed password characters are visible for correction, saved passwords are not displayed, and the manager shows the connected IP address and a green main-screen status indicator. Receiver-saved credentials can be reused too.

**Wi-Fi transmit power:** Dual Boot v2.1 adds **SETTINGS → WIFI POWER** with SAFE - 13 dBm and NORMAL - default. SAFE is the initial manager default and is intended for clone boards that reset or brown out during Wi-Fi transmission. Diamond Radio v1.0.4 has an independent **Settings → WI-FI POWER** option; NORMAL preserves its existing default/adaptive behavior and SAFE fixes the limit at 13 dBm. Lower transmit power can reduce Wi-Fi range. Confirmation on affected clone boards still requires field testing.

**PUBLIC ATS MINI internal OTA warning:** do not use the OTA button inside PUBLIC ATS MINI when you want to keep the firmware in the other slot. Its built-in updater writes the **other** slot and will overwrite Diamond Radio if Diamond is installed there. Dual Boot cannot intercept that write. Always update PUBLIC ATS MINI through the manager's **SAFE OTA** path, selecting the same slot where PUBLIC ATS MINI currently runs. Older manager and Diamond versions do not have this protection. Make a full backup first.

## Safety

Make a full backup before maintenance. Select the layout matching the detected flash capacity, keep USB and power connected, and wait for each operation and its verification to finish. Full Restore, Clean install, and full-flash erase replace the complete flash. The full Dual Boot images contain no receiver firmware in Slot A or B.

Receiver control, FT8, and maps are not part of this maintenance release. Diamond Radio ATS Mini receiver firmware remains available from its [official release repository](https://github.com/khanfar/diamond-radio-ats-mini/releases).

## Legal and third-party notices

See [`legal/THIRD_PARTY_NOTICES.md`](legal/THIRD_PARTY_NOTICES.md), [`legal/DIAMOND_FREEWARE_NOTICE.txt`](legal/DIAMOND_FREEWARE_NOTICE.txt), and the accompanying license texts. Diamond Dual Boot is MIT-licensed; the offline application is freeware with private Diamond-specific source. The separate espflash backend and other third-party components retain their own licenses. No upstream copyright or permission notice is removed or replaced.
