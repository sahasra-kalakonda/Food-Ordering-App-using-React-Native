# Order Taking Mobile App
 
A cross-platform mobile app built with Expo, Expo Router, and Tamagui for taking and managing orders. Features a Firebase backend for real-time data, a React Admin dashboard for management, and full TypeScript support.
 
## Features
 
- **Cross-platform**: Runs on iOS, Android, and Web from a single codebase
- **File-based routing**: Powered by Expo Router for clean, scalable navigation
- **Tamagui UI**: Performant, themeable components with dark/light mode support
- **Firebase backend**: Firestore, Realtime Database, Storage, and Cloud Functions
- **React Admin dashboard**: Web-based admin panel for order/data management
- **React Hook Form**: Efficient, validated form handling
- **TypeScript**: Full type safety throughout the project

## Tech Stack
 
| Technology | Version |
|---|---|
| React Native | ^0.76.5 |
| Expo | ^52.0.23 |
| Expo Router | ^3.1.0 |
| Tamagui | ^1.121.4 |
| Firebase | ^9.6.4 |
| React Admin | ^4.16.20 |
| React Hook Form | ^7.54.2 |
| TypeScript | ^5.7.2 |
| Moment.js | ^2.30.1 |
 
## Project Structure
 
```
├── app/                    # File-based routes (Expo Router)
├── assets/
│   └── images/             # App icon, splash screen, favicon
├── functions/              # Firebase Cloud Functions
├── dist/                   # Web build output (Firebase Hosting)
├── app.json                # Expo configuration
├── babel.config.js         # Babel configuration
├── metro.config.js         # Metro bundler + Tamagui plugin
├── tamagui.config.ts       # Tamagui theme configuration
├── firebase.json           # Firebase Hosting, Functions & Emulator config
├── tsconfig.json           # TypeScript configuration
└── tamagui-web.css         # Generated Tamagui CSS (web)
```
 
## Getting Started
 
### Prerequisites
 
- [Node.js](https://nodejs.org/) (v18+)
- [Expo CLI](https://docs.expo.dev/get-started/installation/)
- [Firebase CLI](https://firebase.google.com/docs/cli) — for backend/emulator usage
- Expo Go on your device, or an iOS/Android simulator
### Installation
 
```bash
# Clone the repository
git clone https://github.com/your-username/order-taking-mobile-app.git
cd order-taking-mobile-app
 
# Install dependencies
npm install
 
# Start the development server
npm start
```
 
Scan the QR code with Expo Go (Android) or the Camera app (iOS).
 
### Running on a specific platform
 
```bash
npm run android   # Android emulator or device
npm run ios       # iOS simulator or device
npm run web       # Browser (localhost)
```
 
## Firebase Setup
 
### Configuration
 
1. Create a Firebase project at [console.firebase.google.com](https://console.firebase.google.com)
2. Add a web app and copy your Firebase config
3. Create a `.env` file (or a `firebaseConfig.ts`) and paste in your credentials:
```ts
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID",
};
```
 
### Local Emulator
 
```bash
# Install Firebase CLI if needed
npm install -g firebase-tools
 
# Start all emulators (Firestore, Functions, Hosting, Storage, etc.)
firebase emulators:start
```
 
Emulator ports:
 
| Service | Port |
|---|---|
| Hosting | 5000 |
| App Hosting | 5002 |
| Functions | 5001 |
| Firestore | 8080 |
| Realtime Database | 9000 |
| Storage | 9199 |
| Emulator UI | Auto |
 
### Deploy to Firebase
 
```bash
# Build the web app and deploy
npm run predeploy   # runs: expo export -p web
firebase deploy
```
 
## Testing
 
```bash
npm test          # Run Jest in watch mode
```
 
Tests use `jest-expo` and `react-test-renderer`.
 
## Configuration Notes
 
- **Routing scheme**: `myapp://` (configured in `app.json` for deep linking)
- **UI style**: `automatic` — respects the device's dark/light mode
- **Path alias**: `@/*` maps to the project root (configured in `tsconfig.json`)
- **Typed routes**: enabled via Expo Router's `experiments.typedRoutes`
---
 
## 📄 License
 
This project is private. All rights reserved.
