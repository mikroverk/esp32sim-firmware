# esp32sim-firmware

Firmware images that [esp32sim](https://github.com/mikroverk/esp32sim) tests and examples use but
do not keep in its own history. esp32sim fetches them by URL pinned to a commit of this repository
and checks each file's SHA-256, the way `tools/fetch-rom-elfs.sh` fetches the mask ROMs; a copy
already present with the right hash is never downloaded again.

The rule in esp32sim: an image the web page runs may be committed there if it is small; anything
over 1 MB, and any set of images only the tests boot, lives here. Each directory holds the images,
a `SHA256SUMS` file, the licence notices for what the images contain, and a README naming the
source example, the IDF version and the configuration of every file.

| Directory | Contents | Fetched by |
| --- | --- | --- |
| `p4/` | ESP32-P4 example images (hello_world on two cores, sd_card, tusb_msc, ESP-Hosted station) and the ESP32-C6 ESP-Hosted slave | `tools/fetch-p4-firmware.sh` |

## Adding an image

1. Put the file in the directory for its chip, with the licence notice for everything it links.
2. Add its line to that directory's `SHA256SUMS` and README (example, IDF version, sdkconfig).
3. Commit, and pin the new commit's hash in the esp32sim fetch script together with the SHA-256.

Files are never changed in place: a rebuilt image gets a new name or a new commit that the fetch
script pins, so an older esp32sim checkout keeps fetching the bytes it was tested with.

Raw URL of a file at a commit: `https://raw.githubusercontent.com/mikroverk/esp32sim-firmware/<commit>/<dir>/<file>`.
