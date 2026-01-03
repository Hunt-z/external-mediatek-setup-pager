# External MediaTek Chip Loader

A simple, robust payload for using external USB Wi-Fi adapters with the WiFi Pineapple.

### Requirements
* **Modern MediaTek Chipsets Only:** This script targets endpoint `.3`, which is standard for modern dual-band chips (e.g., MT7612U, MT7921/AMD RZ608).
* **Supported Drivers:** The device must have kernel support (mt76). Realtek and older chips are **not supported**.

### How it Works
1.  Checks the external USB bus (`1-1.1`) at interface `.3`.
2.  If the device exists, it loads the driver.
3.  **Mirror Mode:** It reads the bands from your Internal Radio (`wlan1mon`) and applies the same bands to the External Radio (`wlan2mon`).
4.  It **never** overrides your Internal Radio settings.

### Troubleshooting
If the script runs but errors with **"Driver Failed to Load"**, your adapter is unsupported or requires a driver not present in the firmware. Unlucky—it won't work.
