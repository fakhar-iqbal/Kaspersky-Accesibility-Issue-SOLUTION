# Kids Shield - Kaspersky Accessibility Watchdog 🛡️

If you're a parent relying on Kaspersky Safe Kids to keep your children safe on Android, you already know the frustration. Every single day, sometimes within hours, the app just... stops. The accessibility permissions get revoked by the phone, and suddenly, your kids are completely unmonitored.

I built this project to fix that exact headache.

*(See the attached screenshots in this repo to see the watchdog in action!)*

## ⚠️ The Real Problem

Newer Android systems (especially Android 13+) have very aggressive battery management. If Android thinks an app is running too much in the background, it silently kills it and strips away its "Accessibility" rights. That’s the core permission Kaspersky needs to monitor screen activity. Once that turns off, the shield drops.

## 🛠️ My Custom Solution

I engineered a dual-app system—a **"Safe Dad"** app for the parent's phone and a hidden **"Safe Kid"** engine for the child’s phone.

It runs a native Kotlin daemon built alongside Flutter that constantly acts as a watchdog. If Android tries to turn off Kaspersky's permissions, my engine uses a one-time ADB (Android Debug Bridge) permission to instantly overwrite the system and force the permissions back on. Zero delay. It even bypasses the 60-second restart delay!

## 📦 How to Download

You don't need to compile any code to use this. I have already built the production apps for you. 

Head over to the **Releases** section on the right side of this GitHub page (or look for the latest release tag) and download these three ready-to-use files:

1. **`Safe_Kid.apk` (The Kids APK):** Install this one on your child's phone.
2. **`Safe_Dad.apk` (The Parents APK):** Install this on your own phone.
3. **`Setup_Guide.zip`:** Download this straight to your Windows laptop.

## 🚀 Setup Guide

Here is exactly how to get it running. It sounds techy, but it’s actually super straightforward.

### Step 1: Prep the Kid's Phone

Plug your child’s phone into your laptop using a USB cable. Go into the phone's settings and turn on **Developer Options** and **USB Debugging**.
*(If you've never done this, just Google "How to enable USB debugging on [Phone Model]"—it usually just involves tapping the "Build Number" 7 times).*

### Step 2: Run the Script

1. On your laptop, unzip the `Setup_Guide.zip` file you downloaded.
2. Inside the unzipped folder, double-click the implementation `.bat` file.
3. A black terminal window will pop up asking to confirm the phone is connected. Just hit any key on your keyboard two or three times when it asks. It will grant the necessary background permissions to the Kid's app and close automatically.
4. You can now unplug the phone.

### Step 3: Pair Them Up

Open the app on both phones! The parent app (`Safe Dad`) will generate a simple 6-digit code. Type that code into the kid's phone to link them together.

And... boom, you're done! You can now access the kid's phone status right from yours. If you watch closely on the kid's phone, you can actually see this engine instantly turning the accessibility features back on if they ever get turned off.

## 💬 Need Help?

If you run into issues, need a customized version for your own family, or just want to chat about how the architecture works under the hood, feel free to reach out!

**Email:** fakhareiqbal3534@gmail.com

**LinkedIn:** www.linkedin.com/in/muhammad-fakhar3534
