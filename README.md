
# Project CleanBrowse: Enhanced Ad-Blocking with Pi-hole and uBlock Origin

Welcome to my **Project CleanBrowse**, where I combine network-wide ad-blocking using **Pi-hole** on a Raspberry Pi 3B+ with **uBlock Origin** in Chrome for a truly seamless ad-free experience. This documentation will guide you through the setup and configuration from scratch, making it replicable for anyone looking to enhance privacy and enjoy cleaner browsing.

---

## Project Overview

**Project Name**: CleanBrowse  
**Goal**: Achieve a more private, ad-free network experience using Pi-hole and uBlock Origin.  
**Technologies**: Pi-hole, Raspberry Pi OS (64-bit Lite), uBlock Origin, Chrome.
![Rpi_project_logo](https://github.com/mohammadajani/CleanBrowse/blob/main/images/Untitled-1.png)

### Hardware & Software
- **Raspberry Pi**: Model 3B+
- **Storage**: 16GB Samsung MicroSD card
- **Power**: Micro USB power supply
- **Networking**: Ethernet cable for stable connection
- **Operating System**: Raspberry Pi OS (64-bit Lite)

![Rpi_project_Hardware](https://github.com/mohammadajani/CleanBrowse/blob/main/images/Rpi_hardware_setup.png)

---

## Step 1: Install Raspberry Pi OS Lite (64-bit)

**Download and Set Up Raspberry Pi Imager**  
1. **Download**: Get the [Raspberry Pi Imager](https://www.raspberrypi.org/software/) for your OS.
![Rpi_imager](https://www.raspberrypi.org/app/uploads/2020/03/RPI_intro-e1583228263677.png)
2. **Insert MicroSD Card**: Connect your 16GB Samsung MicroSD card to your computer.
3. **SSH**: Turn on SSH via RPI-Imager or creating SSH file in bootfs of sdcard.
![Rpi_imager](https://github.com/mohammadajani/CleanBrowse/blob/main/images/Screenshot5.png)
4. **Write OS**: In Raspberry Pi Imager, choose **Raspberry Pi OS Lite (64-bit)** as the OS, select your MicroSD card, and click “Write.”

**Insert Card and Power On Raspberry Pi**  
Once done, insert the MicroSD card into the Raspberry Pi, plug in the Ethernet cable, and power it on.

---

## Step 2: Boot and Configure Raspberry Pi

After booting, access the Raspberry Pi command line via SSH:

```bash
ssh pi@your_rpi_ip_address
```

**Update System**:
```bash
sudo apt update && sudo apt upgrade -y
```

![Terminal Update](https://github.com/mohammadajani/CleanBrowse/blob/main/images/Screenshot6.png)

---

## Step 3: Installing Pi-hole

1. **Get the Installation Command**: The command to install Pi-hole can be found on [Pi-hole's GitHub](https://github.com/pi-hole/pi-hole).
2. **Run Installation**:
   ```bash
   curl -sSL https://install.pi-hole.net | bash
   ```
3. **Setup Wizard**: 
   - Choose **Cloudflare** as your upstream DNS provider (recommended).
   - Follow other prompts as desired.

4. **Save Access Info**: Note down the admin URL and access password at the end of the setup.

![Pi-hole Setup Wizard](https://github.com/mohammadajani/CleanBrowse/blob/main/images/final_Prompt.png)

---

## Step 4: Configuring Pi-hole as DNS Server

Since I didn’t have access to my router’s admin panel, I used the following workaround:

1. **Open Wi-Fi Settings on Mobile Device**: 
2. **Manually Set DNS**: In the DNS settings, input the Raspberry Pi’s IP (192.168.1.4).

![Mobile Wi-Fi Settings](https://github.com/mohammadajani/CleanBrowse/blob/main/images/Screenshot_2024-10-27-18-59-20-036_com.android.settings.jpg)

---

## Step 5: Installing uBlock Origin in Chrome

To block ads on browsers, I added **uBlock Origin** in Chrome:

1. **Visit** [uBlock Origin on Chrome Web Store](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm).
2. **Add Extension**: Click *Add to Chrome* and confirm.

![uBlock Origin Installation](https://github.com/mohammadajani/CleanBrowse/blob/main/images/Screenshot7.png)

---

## Monitoring and Maintenance

- **Access Pi-hole Admin**: Go to `http://<Your_Pi_IP>/admin` for stats and adjustments.
- **Filtering**: You can add or remove domains directly from the Pi-hole dashboard.

---

## Additional Considerations

For further privacy, consider adding browser extensions like **Privacy Badger** or **HTTPS Everywhere**.

---

## Summary

By combining **Pi-hole** with **uBlock Origin**, Project CleanBrowse may not provides absolute privacy by blocking every ads but it will reduce upto 90% of ads with the help of custom adlists enhanced privacy and a smoother browsing experience. Feel free to reach out if you have questions, and enjoy an ad-free network!

---
