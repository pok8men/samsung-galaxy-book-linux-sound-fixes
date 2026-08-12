# Samsung Galaxy Book Lunar Lake (940XHA) Linux Speaker Audio Fix
 
(This guide provides a fix for the internal speaker no-sound issue on the Samsung Galaxy Book Lunar Lake series (model 940XHA) running Linux.)
🛠️ Samsung Galaxy Book Lunar Lake Linux Speaker Fix

This project contains scripts and services to fix the internal speaker audio on Samsung Galaxy Book Lunar Lake laptops running Linux. This guide helps you fix the internal speaker issue on Samsung Galaxy Book devices running Ubuntu/Debian-based distros, where audio doesn't work out-of-the-box due to missing Maxim MAX98390 smart amplifier initialization.

✅ Tested On
* **Device:** Samsung Galaxy Book Lunar Lake (940XHA)
* **Codec:** Realtek ALC298 with Maxim MAX98390 Smart Amps
* **OS:** Ubuntu 24.04+ / Linux Mint / Debian-based distros
* **Kernel:** Linux 6.x+

📦 What This Fix Does
* Installs required DKMS and build prerequisites
* Builds and installs the `snd-hda-scodec-max98390` kernel module
* Configures systemd services to initialize smart amps at boot
* Bridges missing audio routing paths for internal speakers

📦 Folder Structure
text
galaxy-book-lunar-lake-linux-fixes/
└── speaker-fix/
    ├── install.sh
    └── (DKMS and setup scripts)

🚀 How to Use
Download Method: Cloning

Step 1 - Clone:
Bash
```
git clone [https://github.com/Andycodeman/samsung-galaxy-book-linux-fixes.git](https://github.com/Andycodeman/samsung-galaxy-book-linux-fixes.git)
```
Step 2 - Navigate to the speaker-fix folder:
Bash
```

cd samsung-galaxy-book-linux-fixes/speaker-fix
```
Step 3 - Change permission to make script executable:
Bash
```
chmod +x install.sh
```
🖥️ Run the installer script:
Bash
```
sudo ./install.sh
```
This will:
`
`   Install DKMS and kernel headers automatically
`
`   Compile and register the MAX98390 side-codec driver
`
    Set up necessary audio configurations

🔁 Reboot
After setup, reboot your system to apply the audio changes:
Bash

sudo reboot

🧪 Troubleshooting
`
`    Run alsamixer to check if channels are unmuted and volumes are raised.
`
`    Test sound playback using speaker-test -c 2 -t wav or play any media file.
`
`    Ensure Secure Boot compatibility or enroll MOK keys if the DKMS module fails to load on secure boot systems.

🙌 Credit

 `   Original community contributors and developers working on Andycodeman/samsung-galaxy-book-linux-fixes.

📝 License
This project is open-source. Contributions are welcome!
