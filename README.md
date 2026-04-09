# Dual Pixel Studio Link for Unity

Stop emailing yourself sprite sheets. Stop breaking your workflow.

The **Dual Pixel Studio Link** is a lightweight, single-script bridge that connects your Unity project directly to the **Dual Pixel Studio** app on your iPad or iPhone over your local Wi-Fi network. 

Every pixel you draw and frame you animate updates instantly inside Unity. No cables, no manual exporting, no hassle.

<div align="center">
  
  ### 📺 Live Demo
  https://github.com/user-attachments/assets/5a0e99d6-9484-40ef-af51-9adccd694ef4

  <br>
  <em>Draw on your mobile device, see it instantly in Unity.</em>
</div>

## Features

* **Zero Dependencies:** It's just one C# script. No DLLs, no bloated packages, no complicated setup wizards.
* **Live Preview:** Auto-refresh your current sprite directly in the Unity Editor while you draw.
* **Auto-Discovery:** Uses UDP multicast to automatically find your iPad/iPhone on the network. No IP typing required!
* **Engine-Ready Imports:** Automatically slices and configures imported spritesheets with perfect pixel art settings (`FilterMode.Point`, correct `PixelsPerUnit`, uncompressed).

## Quick Start Guide

### 1. Get the App (It's Free)
Download **Dual Pixel Studio** on your iPad or iPhone. It's a professional-grade pixel art editor built specifically for indie game devs. (Zero ads, zero subscriptions).

👉 **[Download 'Dual Pixel Studio' on the App Store]**

### 2. Add the Script to Unity
1. Download the `DualPixelStudioLink.cs` file from this repository.
2. Drag and drop the script into your Unity project. 
   *(Important: It must be placed inside an `Editor` folder, e.g., `Assets/Editor/DualPixelStudioLink.cs`)*

### 3. Connect & Sync
1. In the **Dual Pixel Studio app**, open your project and tap the **Unity Link (Gamepad Icon)** in the toolbar to start the local server.
2. In **Unity**, open the bridge window by navigating to: `Tools > Dual Pixel Studio Link`.
3. Your device should appear automatically under "Available Devices." Click it to connect.
4. Hit **Import Current Frame** or **Import Spritesheet**!

---

## How It Works (The Technical Details)

The Unity Bridge works by communicating with a lightweight HTTP server hosted locally within the Dual Pixel Studio app on your mobile device.

### Supported Endpoints:
The bridge pulls data seamlessly via the following local endpoints:
* `/api/info`: Fetches project metadata (width, height, FPS, frame count).
* `/api/sprite.png`: Fetches the current frame (flattened).
* `/api/sheet.png`: Fetches a full horizontal spritesheet.
* `/api/atlas.json`: Fetches atlas metadata to automatically slice the spritesheet in Unity.

### Network Requirements:
* Your mobile device and your PC/Mac must be on the **same Wi-Fi network**.
* The app uses **Port 8642** (HTTP) for data transfer and **Port 8644** (UDP) for auto-discovery. Ensure these ports are not blocked by your firewall.
* If auto-discovery fails, you can manually enter your device's IP address (displayed in the app) into the Unity window.

---

## 💡 Support the Project

Dual Pixel Studio is completely free, privacy-first, and built by a solo developer. If this tool saves you hours of tedious exporting, consider leaving a tip in the app's "Tip Jar" to unlock a Pixel Pet companion for your home screen!

<p align="center">
  <img src="https://via.placeholder.com/300x150?text=Insert+Pixel+Pet+Image+Here" alt="Pixel Pet" width="300"/>
</p>
