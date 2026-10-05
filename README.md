# Rajarathinam Enterprises Billing

A desktop billing application built with Angular and Electron. In desktop mode, invoices and their product lines are saved to a local SQLite database in Electron's application data folder. The app can list installed printers, send an invoice directly to a selected printer, or open the operating system's print dialog.

## Requirements

- Node.js and npm
- Windows, macOS, or Linux
- A locally installed printer for physical printing

## Run the desktop application

```bash
npm install
npm run desktop
```

The desktop command builds the Angular app and then opens it in Electron. The SQLite database is created automatically on first launch and remains on the computer between app sessions.

## Create a Windows installer

```bash
npm run package:windows
```

This builds a Windows NSIS installer at `release/Rajarathinam-Enterprises-Billing-Setup-1.0.0.exe`. Run the installer and follow the prompts to install the desktop application.

## Browser preview

```bash
npm start
```

The browser preview stores invoices in that browser's local storage and uses its print dialog. It does not access the desktop SQLite database or installed-printer list.

## Android and iOS apps

The mobile apps use Capacitor to run the Angular billing interface as native Android and iOS apps. Each phone stores its invoices and products locally, works offline, and does not sync data with the desktop app or other phones.

### Requirements

- Android: Android Studio with the Android SDK and an emulator or connected device.
- iOS: macOS with Xcode and an iOS simulator or connected device.

### Open a mobile project

```bash
npm install
npm run mobile:android
```

This builds the web app, syncs it into the Android project, and opens Android Studio. Use Android Studio to run the app on an emulator or connected device. For iOS, run `npm run mobile:ios` on a Mac with Xcode installed.

After changing the Angular app, run `npm run mobile:sync` before running it again from Android Studio or Xcode. The generated native projects are in `android/` and `ios/`.

## Billing features

- Create invoices with a date, shop or customer name, product, quantity, and unit price.
- Add multiple product lines; totals are calculated automatically.
- Browse saved invoices and the product names used on them.
- Select an installed printer in Settings or use the system print dialog.
- Print a compact receipt with invoice details and line totals.

## Build and tests

```bash
npm run build
npm test
```
