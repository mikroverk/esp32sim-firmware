# ESP32-P4 example images

The images `tools/fetch-p4-firmware.sh` in esp32sim fetches: the ESP32-P4 examples the emulator's
goldens boot but the web page does not run, plus the ESP32-C6 ESP-Hosted slave they pair with.
Each was built by Xorlev from the example directory named below, under `examples/` in esp32sim,
whose README gives the exact recipe. `SHA256SUMS` lists every file; the fetch script pins the same
hashes.

All P4 images are built for silicon rev < 3 (`CONFIG_ESP32P4_SELECTS_REV_LESS_V3=y`). The
`p4-hello-smp`, `p4-sdcard` and `p4-sdsectors` apps use hello_world's partition table, which is
committed in esp32sim as `web/wasm/fw/public/p4-hello-ptable.bin` (the same bytes).

Licences: the ESP-IDF examples are Unlicense OR CC0-1.0; what they link is listed, with the full
texts, in `hosted-NOTICE.txt` and `p4-usbmsc-NOTICE.txt`. The hello_world and sd_card images link
the same ESP-IDF components as the tusb_msc one, minus TinyUSB; `p4-usbmsc-NOTICE.txt` covers
their texts.

| File | Bytes | Example | Build | Licence |
| --- | ---: | --- | --- | --- |
| `p4-hello-smp-bootloader.bin` | 22976 | `examples/hello_world-p4` | ESP-IDF v5.5.3 get-started/hello_world, both cores (sdkconfig.defaults.smp), rev < 3 | Unlicense OR CC0-1.0 |
| `p4-hello-smp_world.bin` | 168496 | `examples/hello_world-p4` | ESP-IDF v5.5.3 get-started/hello_world, both cores (sdkconfig.defaults.smp), rev < 3 | Unlicense OR CC0-1.0 |
| `p4-sdcard-bootloader.bin` | 22976 | `examples/sd_card-p4` | ESP-IDF v5.5.3 storage/sd_card/sdmmc, rev < 3 | Unlicense OR CC0-1.0 |
| `p4-sdcard.bin` | 300112 | `examples/sd_card-p4` | ESP-IDF v5.5.3 storage/sd_card/sdmmc, rev < 3 | Unlicense OR CC0-1.0 |
| `p4-sdsectors-bootloader.bin` | 22976 | `examples/sd_card-p4-sectors` | sd_card-p4 plus the long sector transfer block, rev < 3 | Unlicense OR CC0-1.0 |
| `p4-sdsectors.bin` | 300832 | `examples/sd_card-p4-sectors` | sd_card-p4 plus the long sector transfer block, rev < 3 | Unlicense OR CC0-1.0 |
| `p4-usbmsc-bootloader.bin` | 22976 | `examples/usb_msc-p4` | ESP-IDF v5.5.3 peripherals/usb/device/tusb_msc on SDMMC, esp_tinyusb 2.4.0, tinyusb 0.21.0~2, rev < 3 | see p4-usbmsc-NOTICE.txt |
| `p4-usbmsc-ptable.bin` | 3072 | `examples/usb_msc-p4` | ESP-IDF v5.5.3 peripherals/usb/device/tusb_msc on SDMMC, esp_tinyusb 2.4.0, tinyusb 0.21.0~2, rev < 3 | see p4-usbmsc-NOTICE.txt |
| `p4-usbmsc.bin` | 428192 | `examples/usb_msc-p4` | ESP-IDF v5.5.3 peripherals/usb/device/tusb_msc on SDMMC, esp_tinyusb 2.4.0, tinyusb 0.21.0~2, rev < 3 | see p4-usbmsc-NOTICE.txt |
| `c6-hosted-bootloader.bin` | 24192 | `examples/esp-hosted-p4` | esp_hosted 2.12.13 slave example for the ESP32-C6 | see hosted-NOTICE.txt |
| `c6-hosted-ptable.bin` | 3072 | `examples/esp-hosted-p4` | esp_hosted 2.12.13 slave example for the ESP32-C6 | see hosted-NOTICE.txt |
| `c6-hosted-otadata.bin` | 8192 | `examples/esp-hosted-p4` | esp_hosted 2.12.13 slave example for the ESP32-C6 | see hosted-NOTICE.txt |
| `c6-hosted-slave.bin` | 1208832 | `examples/esp-hosted-p4` | esp_hosted 2.12.13 slave example for the ESP32-C6 | see hosted-NOTICE.txt |
| `c6-hosted-rawtp-slave.bin` | 1211904 | `examples/esp-hosted-p4` | esp_hosted 2.12.13 slave example for the ESP32-C6, raw throughput test on | see hosted-NOTICE.txt |
| `p4-hosted-bootloader.bin` | 22976 | `examples/esp-hosted-p4` | ESP-IDF v5.5.3 wifi/getting_started/station with esp_hosted 2.12.13, rev < 3 | see hosted-NOTICE.txt |
| `p4-hosted-ptable.bin` | 3072 | `examples/esp-hosted-p4` | ESP-IDF v5.5.3 wifi/getting_started/station with esp_hosted 2.12.13, rev < 3 | see hosted-NOTICE.txt |
| `p4-hosted-station.bin` | 655952 | `examples/esp-hosted-p4` | ESP-IDF v5.5.3 wifi/getting_started/station with esp_hosted 2.12.13, rev < 3 | see hosted-NOTICE.txt |
| `p4-hosted-rawtp-rx.bin` | 657184 | `examples/esp-hosted-p4` | ESP-IDF v5.5.3 wifi/getting_started/station with esp_hosted 2.12.13, raw throughput test on, rev < 3 | see hosted-NOTICE.txt |
| `p4-hosted-rawtp-tx.bin` | 657184 | `examples/esp-hosted-p4` | ESP-IDF v5.5.3 wifi/getting_started/station with esp_hosted 2.12.13, raw throughput test on, rev < 3 | see hosted-NOTICE.txt |
