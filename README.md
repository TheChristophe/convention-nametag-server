## Small nametag using Pi Zero W and various OLED panels

Work-in-progress self-programmed convetion nametag using a Raspberry Pi Zero W and a SSD1322 OLED panel. The intended
use is pinning it to a shirt or hanging it around your neck and uploading files using your phone.

#### Current state

- Recycled old gl nametag code
- Proof of concept done:

https://user-images.githubusercontent.com/65168240/141864525-b1e3a986-ae35-4b9f-8bda-cf15c19f3d5e.mp4


TODO:

- Playlist functionality
- Frontend application / website interface (using React)

### OLED Panels

Panels tried during development:

- [SH1106 HAT](https://www.waveshare.com/1.3inch-oled-hat.htm)
- [SSD1305 HAT](https://www.waveshare.com/2.23inch-oled-hat.htm)
- Soldered SSD1322
  using [this guide](https://www.balena.io/blog/build-a-raspberry-pi-powered-train-station-oled-sign-for-your-desk/)

### Frontend

TODO

### Backend

- Set up cross-compilation
    - I refer you to [crosstool-ng](https://github.com/crosstool-ng/crosstool-ng) and wish you the best of luck
        - Pick [this](https://github.com/crosstool-ng/crosstool-ng/tree/master/samples/armv6-unknown-linux-gnueabihf)
          or [this](https://github.com/crosstool-ng/crosstool-ng/tree/master/samples/armv6-unknown-linux-gnueabi) config
- Build with cmake using provided toolchain file

Run with:

- `sudo ./nametag` (due to GPIO permissions)

Notes:

- Ensure your video is already in desired size
    - From testing, h264 decode for 256x64 in software takes about ~5ms. 480x360 requires about 33ms
    - In combination with 4.5ms copy time, this means <10ms, allowing for up to 100fps
