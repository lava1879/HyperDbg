# HyperDbg v0.25.1 with USB debugging is released!

This release is based on **HyperDbg** v0.25.1 and adds debugging over a USB 3.0 cable. Please visit the [README](https://github.com/lava1879/HyperDbg#readme) to set up the USB connection, and [Build & Install](https://docs.hyperdbg.org/getting-started/build-and-install) to configure the environment for running **HyperDbg**. Check out the [Quick Start](https://docs.hyperdbg.org/getting-started/quick-start) and [Frequently Asked Questions (FAQs)](https://docs.hyperdbg.org/getting-started/faq) to learn more.

The release package includes `hyperdbg-usb.inf` and `hyperdbg-usb-install.ps1`, which install the WinUSB driver on the debugger.

This release builds on the outstanding work of [@SinaKarvandi](https://github.com/SinaKarvandi) and all contributors of the original [HyperDbg](https://github.com/HyperDbg/HyperDbg) project.

### Added
- Added debugging support via a USB cable using the Intel xHCI Debug Capability Interface (DBC) ([link](https://github.com/lava1879/HyperDbg/commit/753222631bb1706bba4473f27b8a507dbe47583d))([link](https://github.com/lava1879/HyperDbg/commit/fe2a82dfbfba1f038e6f3361bc6806f226c04ee4))([link](https://github.com/lava1879/HyperDbg/commit/7f1cc7752078d4ca6a6105eab697dd4c86667068))([link](https://github.com/lava1879/HyperDbg/commit/a8dc9ea0764f15606df6ac8cb9a967d6eeb64343))([link](https://github.com/lava1879/HyperDbg/commit/c1a8e052f979ff43536f98145c214bc3799da6dd))([link](https://github.com/lava1879/HyperDbg/commit/00f9523da38aa14584350ca06ef22dc01de7891b))

### Changed
- Fix halting on NMI and hardware exception vm-exits, keep the MTF request of a halt NMI that arrives in vmx-root, and fix the halt and continue race and the stale step-over breakpoint ([link](https://github.com/lava1879/HyperDbg/commit/f8f329cd557883336e5c92c132eadbe8b18f8e2e))([link](https://github.com/lava1879/HyperDbg/commit/e59220935e3bb0d2d9c3acd6f437f810a1fa994b))([link](https://github.com/lava1879/HyperDbg/commit/3cdd35f175863cb4d963519f8fa6fd4ca5b38ea1))
- Wait until halted cores finish a synchronized task, and receive debugger commands under DebuggerResponseLock ([link](https://github.com/lava1879/HyperDbg/commit/b892f4345f1a5cc19498e988b4920aa2492f9ee2))([link](https://github.com/lava1879/HyperDbg/commit/acbec71f3fa84872b7b563fc5b552f12c3b649ce))
- Fix interrupt delivery by checking the whole pending interrupt queue, not injecting an external interrupt in an STI shadow, and delivering queued interrupts in APIC priority order above the TPR ([link](https://github.com/lava1879/HyperDbg/commit/cc11821bc5b294eac5b0ee4f29f317f292d0d0c4))([link](https://github.com/lava1879/HyperDbg/commit/7401100f1d9f62010a00f0bacdb218e99e5cb965))([link](https://github.com/lava1879/HyperDbg/commit/347cc27fb65029ad2cc0e56ecea57c661f23fe9e))
- Deliver the guest's own #DB after halting on it ([link](https://github.com/lava1879/HyperDbg/commit/be8a05b036d2f0b7ccc6f7ad919c088b78f44319))
- Unload KD on the debuggee when the debugger closes the connection, and do not halt again after the debugger closes the connection ([link](https://github.com/lava1879/HyperDbg/commit/3e12a2eeb5fe9851c4b018b8df0b13e2dcee0176))([link](https://github.com/lava1879/HyperDbg/commit/9c85e61cb80581c7335e6aadb4c8b74d04d16c42))
- Stop on vm-entry failures instead of retrying forever ([link](https://github.com/lava1879/HyperDbg/commit/f89d3cce75ea33cef7fc1c3fb4c00a4be8e03312))
- Allocate the EPT identity table from non-paged pool to fix "Err, unable to allocate memory for EPT" after long uptime ([link](https://github.com/lava1879/HyperDbg/commit/0d8423db32beee7f24dec4d71a3654e56f00a9dc))
