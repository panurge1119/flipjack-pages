# FlipJack Roon Setup Guide

This guide explains how to install and run the open-source `roon-extension-http-api` bridge so FlipJack on Apple TV can connect to your Roon system.

## Before you start

You will need:

- A **Mac mini, Mac, NAS, or Raspberry Pi** on the same local network as your **Roon Core**
- **Roon Core** already installed and running
- **Node.js** and **npm** installed on the device that will run the bridge
- Access to **Terminal** on that device
- Your **Apple TV** running FlipJack on the same network

## What this setup does

FlipJack does not connect directly to Roon Core by itself. Instead, it connects through the open-source `roon-extension-http-api` bridge.

That bridge:

- runs on your local network
- discovers your Roon zones
- exposes a local web address FlipJack can use

By default, the bridge runs on **port 3001**.

## Step 1: Open Terminal on the device that will run the bridge

On your Mac mini or other bridge device, open **Terminal**.

You will enter the commands below exactly as shown.

## Step 2: Download the bridge software

Run these commands:

```bash
git clone https://github.com/st0g1e/roon-extension-http-api.git
cd roon-extension-http-api
```

What this does:

- `git clone ...` downloads the bridge from GitHub
- `cd roon-extension-http-api` moves you into the project folder

If you get an error saying `git` is not found, install Git first and then run the commands again.

## Step 3: Install the required packages

Run:

```bash
npm install
```

What this does:

- downloads and installs the Node.js packages the bridge needs

This may take a minute.

If you get an error saying `npm` is not found, install Node.js first, then return to this folder and run the command again.

## Step 4: Start the bridge

Run:

```bash
node .
```

If successful, the bridge will start and listen on **port 3001**.

Leave this Terminal window open while testing, unless you later configure the bridge to run automatically in the background.

## Step 5: Enable the extension in Roon

Once the bridge is running:

1. Open the **Roon** app.
2. Go to **Settings**.
3. Select **Extensions**.
4. Look for **HTTP API**.
5. Click **Enable**.

If you do not see **HTTP API** in Roon:

- confirm the bridge is still running in Terminal
- confirm the bridge device is on the same network as Roon Core
- try restarting the bridge with `node .`

## Step 6: Test that the bridge is working

On the same device running the bridge, open a web browser and go to:

```text
http://localhost:3001/roonAPI/listZones
```

If setup is working, you should see **JSON output** listing your Roon zones.

This confirms:

- the bridge is running
- the local web API is working
- Roon zones are available to FlipJack

If the page does not load:

- make sure the Terminal window is still running `node .`
- make sure the extension is enabled in Roon
- make sure port `3001` is not blocked by another service

## Step 7: Find the local IP address of the bridge device

FlipJack on Apple TV needs the local network address of the device running the bridge.

On the bridge device, run:

```bash
ifconfig
```

Look for the active network adapter and find its `inet` IPv4 address.

It will usually look something like:

```text
192.168.1.159
```

That is the address you will use in FlipJack.

Tips:

- Ignore `127.0.0.1`, that is only the device’s internal loopback address
- If you see more than one local address, use the one for the network connection you are actively using
- On many Macs this is often under `en0` or `en1`

## Step 8: Enter the bridge URL in FlipJack on Apple TV

On Apple TV in **FlipJack**:

1. Go to **Settings**.
2. Open **Music Source**.
3. Choose **Roon**.
4. Enter the bridge URL in this format:

```text
http://[your-local-ip]:3001
```

Example:

```text
http://192.168.1.159:3001
```

Do not enter `localhost` on Apple TV. `localhost` on Apple TV refers to the Apple TV itself, not your Mac mini or other bridge device.

## Step 9: Test FlipJack

After entering the bridge URL:

1. Save the setting in FlipJack
2. Test the Roon connection
3. Confirm that your zones appear and that FlipJack can connect

If FlipJack cannot connect:

- recheck the IP address you entered
- confirm the bridge is still running
- confirm the bridge device and Apple TV are on the same local network
- confirm the Roon extension is enabled

## Optional: Keep the bridge running after restart with pm2

If you want the bridge to start automatically after reboots, use **pm2**.

### Install pm2

Run:

```bash
npm install -g pm2
```

### Start the bridge with pm2

From inside the `roon-extension-http-api` folder, run:

```bash
pm2 start "node ." --name roon-bridge
```

### Enable automatic startup after reboot

Run:

```bash
pm2 startup
```

`pm2` will print another command for you to run. Copy and run that command exactly as shown.

### Save the process list

Run:

```bash
pm2 save
```

After that, the bridge should restart automatically after reboot.

## Alternative: Start it manually when needed

If you do not want to use `pm2`, you can simply start the bridge manually whenever needed:

```bash
cd roon-extension-http-api
node .
```

This is fine if you only use FlipJack occasionally.

## Troubleshooting

### I do not see "HTTP API" in Roon

- make sure `node .` is still running
- make sure the bridge device and Roon Core are on the same network
- try restarting both the bridge and the Roon app

### The browser test works on the Mac, but FlipJack cannot connect

- make sure you used the Mac mini’s local IP, not `localhost`
- make sure you included `:3001`
- make sure the Apple TV is on the same network

### I do not know which IP address to use

Use `ifconfig` and look for the active interface’s `inet` address. In most home networks, it will look like `192.168.x.x`.

### The bridge stops when I close Terminal

That is expected if you started it with `node .`. Use `pm2` if you want it to keep running in the background.

## Summary

The basic setup is:

1. Clone the bridge repo
2. Run `npm install`
3. Start it with `node .`
4. Enable **HTTP API** in Roon
5. Test `http://localhost:3001/roonAPI/listZones`
6. Enter `http://[your-local-ip]:3001` in FlipJack

Once those steps work, FlipJack should be able to connect to Roon through the bridge.
