# Custom Debian GNOME ISO for Dell Inspiron 5301

Tailored custom Linux distribution ISO optimized specifically for **Dell Inspiron 5301 (11th Gen Intel Core i5, Intel Iris Xe Graphics, 8GB RAM)**.

---

## 🚀 Tailored Hardware & Performance Customizations

### 1. 8GB RAM Optimization
- **ZRAM with Zstandard (zstd) Compression:** Allocates 100% of RAM as a compressed pool, effectively expanding usable memory to ~12–14GB without slow disk swapping.
- **Aggressive Kernel Memory Management (`vm.swappiness = 180`):** Prioritizes in-memory compression to prevent multitasking freezes.
- **EarlyOOM Daemon:** Automatically manages high-memory pressure to keep the desktop responsive under heavy workloads.

### 2. Intel Iris Xe & Core i5 Graphics
- **Hardware Video Acceleration:** Pre-configured `LIBVA_DRIVER_NAME=iHD` with `intel-media-va-driver-non-free`.
- **Battery-Saving YouTube & Video Playback:** Hardware decoding for AV1, VP9, HEVC/H.265, and H.264 offloads work from the CPU to the Iris Xe GPU.
- **Wayland Native:** Smooth 60fps animations with Wayland on GNOME 43+.

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

### Step 1: Create a GitHub Repository
1. Go to [github.com/new](https://github.com/new).
2. Repository name: `dell-5301-linux` (or any name you choose).
3. Set to **Public** (for unlimited free build minutes).
4. Do **not** initialize with a README (this repository already has everything).
5. Click **Create repository**.

### Step 2: Push This Repository
Run these commands from your terminal:

```bash
cd /data/data/com.termux/files/home/custom-linux-iso
git remote add origin https://github.com/<YOUR_GITHUB_USERNAME>/dell-5301-linux.git
git push -u origin main
```

*(If using a Personal Access Token or SSH key, authenticate when prompted).*

### Step 3: Trigger the Cloud Build
1. In your GitHub repository, click on the **Actions** tab.
2. Select **Build Custom Linux ISO** on the left.
3. Click **Run workflow** -> **Run workflow**.

GitHub will spawn a 4-vCPU 16GB runner, build the complete live hybrid ISO, generate SHA256 checksums, and publish it under the **Releases** tab as a downloadable `.iso`!

### (Optional) Step 4: Enable Google Drive Upload
If you want the ISO automatically uploaded to your Google Drive upon completion:
1. Copy your `rclone.conf` containing your Google Drive token.
2. In your repo: **Settings → Secrets and variables → Actions → New repository secret**.
3. Name: `RCLONE_CONFIG`
4. Value: Paste your `rclone.conf` contents.
