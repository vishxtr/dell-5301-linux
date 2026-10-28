# Custom Debian GNOME ISO for Dell Inspiron 5301

Tailored custom Linux distribution ISO optimized specifically for **Dell Inspiron 5301 (11th Gen Intel Core i5, Intel Iris Xe Graphics, 8GB RAM)** with built-in **Android & Windows integration**.

---

## 📱 Android & 🪟 Windows Integration

### 1. Run Android Apps Natively (Waydroid)
- **Native Android Container:** Pre-configured with **Waydroid** for running Android apps alongside Linux desktop apps.
- **GPU Accelerated:** Full hardware rendering on Intel Iris Xe under GNOME Wayland (no lag, no slow emulation).
- **Multi-Window Integration:** Android apps open in their own windows just like standard Linux apps.

### 2. Android Screen Mirroring & PC Control (Scrcpy)
- **High-Performance Mirroring:** **Scrcpy** pre-installed for ultra-low-latency 60fps mirroring over USB or Wi-Fi.
- **Audio & Control Forwarding:** Full keyboard, mouse, and audio forwarding with Android clipboard synchronization.
- **Plug & Play ADB:** Pre-installed udev rules allow immediate USB connection without permissions issues.

### 3. Seamless Phone ↔ PC Integration (GSConnect)
- **Shared Clipboard:** Copy text on your Android phone and paste it directly on your laptop (and vice-versa).
- **Notification Sync:** View and reply to phone notifications directly from the GNOME notification tray.
- **Wireless File Transfers:** Send files between phone and PC with a right-click.
- **SMS & Media Control:** Send SMS messages from your laptop and control laptop volume/media from your phone.

### 4. Windows App Compatibility (Wine & Bottles)
- **Full 32-bit & 64-bit Wine:** Pre-configured `wine`, `wine32`, `wine64`, and `winetricks` for running Windows `.exe` and `.msi` programs.
- **Flathub Enabled:** Ready for 1-click installation of **Bottles** (sandboxed Windows app manager) or Lutris/Heroic.

---

## 🚀 Dell Inspiron 5301 Hardware & Performance Customizations

### 1. 8GB RAM Optimization
- **ZRAM with Zstandard (zstd) Compression:** Allocates 100% of RAM as a compressed pool, effectively expanding usable memory to ~12–14GB without slow disk swapping.
- **Aggressive Kernel Memory Management (`vm.swappiness = 180`):** Prioritizes in-memory compression to prevent multitasking freezes.
- **EarlyOOM Daemon:** Automatically manages high-memory pressure to keep the desktop responsive under heavy workloads.

### 2. Intel Iris Xe & Core i5 Graphics
- **Hardware Video Acceleration:** Pre-configured `LIBVA_DRIVER_NAME=iHD` with `intel-media-va-driver-non-free`.
- **Battery-Saving YouTube & Video Playback:** Hardware decoding for AV1, VP9, HEVC/H.265, and H.264 offloads work from the CPU to the Iris Xe GPU.
- **Wayland Native:** Smooth 60fps animations with Wayland on GNOME.

### 3. Dell Laptop Hardware & Thermals
- **Intel Sound Open Firmware (`firmware-sof-signed`):** Fixes 11th Gen Tiger Lake microphone and speaker issues.
- **Intel Wi-Fi 6 (AX201) & Bluetooth:** `firmware-iwlwifi` pre-installed for instant out-of-the-box Wi-Fi.
- **Thermald & Power Profiles Daemon:** Prevents overheating and optimizes battery life with GNOME power mode switching (Power Saver / Balanced / Performance).
- **Precision Touchpad Gestures:** Tap-to-click, natural scrolling, and smooth 1:1 multi-finger gestures enabled by default.

### 4. Desktop & Experience
- **GNOME Desktop:** Dark mode enabled by default, Inter UI font, JetBrains Mono coding font, and Papirus icons.
- **PipeWire Audio:** Modern, low-latency audio stack with Bluetooth LDAC/AAC codec support.
- **Calamares Installer:** Simple graphical installer supporting dual-boot alongside Windows with automatic UEFI detection.

---

## ☁️ How to Build on GitHub Cloud

### Trigger the Cloud Build
1. In your GitHub repository, click on the **Actions** tab:
   **[https://github.com/vishxtr/dell-5301-linux/actions](https://github.com/vishxtr/dell-5301-linux/actions)**
2. Select **Build Custom Linux ISO** on the left.
3. Click **Run workflow** -> **Run workflow**.

GitHub will compile the live hybrid ISO and upload it under the **Releases** tab for direct download.
