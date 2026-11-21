# HyperDbg v0.25.2 is released!

This release is based on **HyperDbg** v0.25.1 and makes the USB 3.0 connection more reliable. Please visit the [README](https://github.com/lava1879/HyperDbg#readme) to set up the USB connection, and [Build & Install](https://docs.hyperdbg.org/getting-started/build-and-install) to configure the environment for running **HyperDbg**. Check out the [Quick Start](https://docs.hyperdbg.org/getting-started/quick-start) and [Frequently Asked Questions (FAQs)](https://docs.hyperdbg.org/getting-started/faq) to learn more.

The release package includes `hyperdbg-usb.inf` and `hyperdbg-usb-install.ps1`, which install the WinUSB driver on the debugger.

This release builds on the outstanding work of [@SinaKarvandi](https://github.com/SinaKarvandi) and all contributors of the original [HyperDbg](https://github.com/HyperDbg/HyperDbg) project.

### Added
- Added a USB configuration timeout that turns DbC off and on again when the debugger connects but does not configure the device in time, as described in xHCI 1.2 section 7.6.4.1 ([link](https://github.com/lava1879/HyperDbg/commit/2bc914cd700f3d293f3ce24d6691cd110a0b7650))

### Changed
- Do not hang the debugger when the USB device disconnects, and report a lost reply instead of waiting for it forever ([link](https://github.com/lava1879/HyperDbg/commit/19470ec0ba1a509f4fc6345572ac57ae2f27e240))
- Fix bug checks when the driver unloads while the VMM is still running and when a second instance of the driver starts ([link](https://github.com/lava1879/HyperDbg/commit/f3c1dfc89eba1c4fd104a57dc2d9b2f328aa4b73))([link](https://github.com/lava1879/HyperDbg/commit/b735122cb10e84ff608abcdb49e0dac4a1fa46fb))
- Wait for the old hyperkd service to be deleted before installing it again ([link](https://github.com/lava1879/HyperDbg/commit/e97ff2c9d6e0bc3ad673525aa2b3c985fba11abd))
