# LakeLifterBridge Firmware Binaries

Firmware binaries used by the LakeLifterBridge Android app for 2-step device updates.

## v15tov21/

Firmware chain for updating old BMC6 devices (v015) to production firmware (v020a+).

| File | Description |
|------|-------------|
| `repartition.bin` | Repartition firmware — repartitions flash from 1.9MB to 3.75MB app slots |
| `production.bin` | Production firmware — the new firmware to install after repartition |

### Update Flow
1. App pushes `repartition.bin` to device via BLE trigger + WiFi
2. Device reboots, repartitions flash, starts Soft AP
3. App pushes `production.bin` to device via WiFi
4. Device installs production firmware, reboots into new firmware
