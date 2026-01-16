# 🛸 Antigravity Shit-Chat Mobile Monitor

[![Node.js](https://img.shields.io/badge/Node.js-v16%2B-green.svg)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-4.x-blue.svg)](https://expressjs.com/)
[![WebSocket](https://img.shields.io/badge/WebSocket-WS-orange.svg)](https://github.com/websockets/ws)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **"Because great code doesn't wait for your bathroom break."**

Antigravity Shit-Chat is a real-time mobile interface designed specifically for monitoring and interacting with Antigravity chat sessions. Whether you're grabbing lunch or taking a break, keep your AI's progress in your pocket.

<p align="center">
  <img width="800" alt="Antigravity Shit-Chat Preview" src="https://github.com/user-attachments/assets/95318065-d943-43f1-b05c-26fd7c0733dd" />
</p>

## ✨ Features

- **📱 Mobile Optimized**: A sleek, responsive UI built for modern mobile browsers.
- **🔄 Real-Time Snapshots**: Polls the workbench every 3 seconds and updates your view via WebSockets.
- **⌨️ Remote Interaction**: Inject messages directly into the Antigravity Lexical editor from your phone.
- **🎨 Visual Fidelity**: Captures and synchronizes CSS styles to maintain the "Antigravity" look and feel.
- **📜 Intelligent Scrolling**: Auto-scrolls to the bottom on new messages, but stays put when you're manually reading history.

## 🛠️ How It Works

The system operates through three primary layers:

1.  **Snapshot Capture (CDP)**: The server connects to the Antigravity instance via the **Chrome DevTools Protocol (CDP)**. It identifies the `#cascade` container and exports its HTML/CSS state.
2.  **Smart Injection**: Messages sent from the mobile UI are injected via a bridge script that handles the Lexical text editor state and triggers the submission logic inside the workbench.
3.  **WebSocket Sync**: A lightweight WebSocket server notifies the client whenever the chat content changes, ensuring minimal data usage and maximum responsiveness.

## 🚀 Getting Started

### 1. Enable Remote Debugging
Antigravity must be started with the remote debugging port enabled so the monitor can "see" inside:

```bash
antigravity . --remote-debugging-port=9000
```

### 2. Install & Start
Clone the repo and install the minimal dependencies:

```bash
# Install dependencies
npm install

# Start the server
npm start
```

### 3. Access on Mobile
Find your local IP address and open it in your mobile browser:

```text
http://<your-local-ip>:3000
```
*Note: Your mobile device and computer must be on the same local network.*

## 💡 Troubleshooting

- **CDP Not Found**: Ensure Antigravity is actually running and the port matches (defaults to 9000).
- **Not Loading on Mobile**: Check your firewall settings. Port `3000` must be accessible.
- **White Screen**: The snapshot only triggers when a chat session is active and the `#cascade` element exists.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

<p align="center">Built with ☕ and necessity.</p>
