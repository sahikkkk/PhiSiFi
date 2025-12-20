# 🔓 WIFI HIJACK v1.0

<p align="center">
  <a href="https://github.com/p3tr0s/WIFI-HIJACK-v.01">
    <img src="https://img.shields.io/badge/Tool-WIFI%20HIJACK%20v1.0-brightgreen" alt="Tool">
  </a>
  <img src="https://img.shields.io/badge/Version-1.0-green" alt="Version">
  <img src="https://img.shields.io/badge/Support-None-red" alt="Support">
  <img src="https://img.shields.io/badge/Platform-ESP8266-blue" alt="Platform">
</p>

---

## 📌 Overview

**WIFI HIJACK v1.0** is a proof-of-concept ESP8266 firmware that combines  
**Deauthentication** and **Evil-Twin Captive Portal** techniques into a single workflow.

This project is a *“franken-baby”* of:

- https://github.com/M1z23R/ESP8266-EvilTwin  
- https://github.com/adamff1/ESP8266-Captive-Portal  

Built for **learning, experimentation, and demonstration purposes**.

<p align="center">
  <img src="https://i.pinimg.com/736x/94/72/3d/94723d53298ed9cb9d59e00feef34b28.jpg" width="800">
</p>

---

## ⚙️ How It Works

The firmware runs on an **ESP8266** and performs:

- 📡 Deauthentication attacks on a selected Wi-Fi AP  
- 🧪 Evil-Twin access point creation  
- 🔐 Captive portal password capture with live verification  

Both attacks can run **simultaneously** — no toggling required.

---

## ✨ Features

- ✔ Deauthentication of target Wi-Fi access point  
- ✔ Evil-Twin AP with captive portal  
- ✔ Password verification against original AP  
- ✔ Deauth + Evil-Twin at the same time  
- ✔ Web-based control panel  

---

## ⚠️ DISCLAIMER

> **FOR EDUCATIONAL PURPOSES ONLY**

- Use **only** on networks you own or have permission to test.
- Unauthorized use may be **illegal**.
- The author takes **no responsibility** for misuse.

Check your local laws before using this tool.

---

## 🛠 Installation (Arduino IDE)

1. Install **Arduino IDE**
2. Go to `File → Preferences`
3. Add this URL to **Additional Boards Manager URLs**:
`https://raw.githubusercontent.com/SpacehuhnTech/arduino/main/package_spacehuhn_index.json `
4. Go to `Tools → Board → Boards Manager`
5. Install **ESP8266 Deauther**
6. Open: `ESP8266_WIFI_HIJACK_v.01.ino `
7. Select board: `Tools → Board → ESP8266 Deauther `
8. Select correct **COM Port**
9. Click **Upload**

---

## 🚀 How to Use

1. Power on the ESP8266
2. Connect to Wi-Fi:
   ------
**Default Access Point Configuration**

| Parameter | Value |
|---------|-------|
| SSID | `JONNY-JONNY YES PAPA!` |
| Password | `sahikisdev12` |

---

3. Open browser: 192.168.4.1
4. Select target AP *(refresh page every 30 seconds)*
5. Click **Start Deauthing**
6. Click **Start Evil-Twin**
7. Optionally connect to the cloned open AP
8. Stop attacks by:
- Visiting `192.168.4.1/admin`
- Resetting the ESP8266

---

## 🔑 Password Capture

- When a valid password is found:
- Evil-Twin stops
- Default AP restarts
- Captured credentials appear in the web UI

⚠ Data is stored in RAM — power loss resets everything.

---


## 🧭 Attack Workflow

To ensure proper operation, follow the steps below **in order**:

### Step 1: Start Deauthentication
- Select the target Wi-Fi access point from the available networks list.
- Click **Start Deauthing** to disconnect clients from the target network.
- Keep deauthentication running to increase the effectiveness of the Evil-Twin attack.

### Step 2: Launch Evil-Twin Access Point
- Click **Start Evil-Twin** after deauthentication has begun.
- A cloned access point (open network) using the target SSID will be created.
- Victims attempting to reconnect will be redirected to the captive portal.

> ⚠️ **Important:**  
> Running deauthentication **before** launching the Evil-Twin significantly improves success rate.

---

## ❌ It Doesn’t Work?

- This is a **POC**
- **No support is provided**
- Modern routers may block deauth attacks

Read first:
https://blog.spacehuhn.com/deauth-attack-not-working

---

## 🙏 Credits

- https://github.com/SpacehuhnTech/esp8266_deauther  
- https://github.com/M1z23R/ESP8266-EvilTwin  
- https://github.com/adamff1/ESP8266-Captive-Portal  
