# Ropeless Fishing Gear App

## Overview
The Ropeless Fishing Gear App is designed to help manage and control your fishing traps using Bluetooth-enabled nanomodems. This guide will walk you through the steps to use the app effectively.

## App Usage 

### 1. Ensure Bluetooth is Enabled
Make sure that Bluetooth is enabled on your mobile device.

### 2. Power Up the Nanomodem
Power up the nanomodem. Your mobile device should connect to it automatically via Bluetooth.

### 3. Add a New Trap
Select the add button located at the bottom of the control panel to add a new trap. Ensure that the ID you enter matches the address on your physical trap.

### 4. View and Select the Trap
Once a new trap has been added, you should be able to view and select it from the control panel.

### 5. Release / Set Your Trap
Select the desired trap from the control panel and press the circular blue button to perform the desired operation.

### 6. Monitor the Trap Status
Monitor the state of your physical trap and confirm the success or failure of the operation. The status of your trap will be updated accordingly within the app.

## Development Guide

### Project Setup
- Ensure `package.json` and `app.json` are correctly configured.
- Verify project directory structure.

### Cleaning and Reinstalling Dependencies
```
# Remove and reinstall node modules
rm -rf node_modules
npm install

# Remove and reinstall pods (from the ios directory)
cd ios
rm -rf Pods
pod install --repo-update
cd ..
```
## Starting Metro Bundler
```
# Clear Metro Bundler cache and start it
npx expo start --clear
#npx expo start --dev-client
```
## Building and Running the App
```
# Rebuild and run the app on your device
npx expo run:ios --device
```
## Configuration Details
Info.plist
Add necessary usage descriptions for accessing privacy-sensitive data:
```
<key>NSBluetoothAlwaysUsageDescription</key>
<string>This app uses Bluetooth to connect to devices.</string>
<key>NSBluetoothPeripheralUsageDescription</key>
<string>This app uses Bluetooth to connect to devices.</string>
<key>NSLocationWhenInUseUsageDescription</key>
<string>This app uses your location to provide location-based features.</string>
<key>NSLocationAlwaysUsageDescription</key>
<string>This app uses your location to provide location-based features even when the app is in the background.</string>
```
## Expo.plist

Ensure EXUpdatesURL and EXUpdatesSDKVersion are correctly set:
```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>EXUpdatesSDKVersion</key>
    <string>50.0.0</string>
    <key>EXUpdatesURL</key>
    <string>https://u.expo.dev/a2a705c5-fa40-456b-9053-74290681cb77</string>
</dict>
</plist>
```
## Tips

    Ensure Info.plist and Expo.plist are Correctly Configured:
        Add necessary usage descriptions for accessing privacy-sensitive data like Bluetooth and Location services.
    Use viewDidAppear for presenting view controllers to ensure the view hierarchy is set up.
