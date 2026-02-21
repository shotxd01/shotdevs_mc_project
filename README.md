# Minecraft AFK Bot Admin Dashboard

A budget-friendly, secure, and feature-rich admin dashboard to control and monitor a Minecraft AFK bot using Mineflayer. Built with Node.js, Express, EJS, and Tailwind CSS.

## 🚀 Features

- **Admin Dashboard**: Secure login system.
- **Bot Control**: Start, Stop, Restart, and Toggle AFK mode.
- **Live Console**: Real-time logs and chat capability.
- **Server Settings**: Configure Server IP, Port, Version, and Microsoft Account.
- **Microsoft Authentication**: Built-in flow for first-time verification.
- **Dark Mode**: Enabled by default with persistent settings.
- **MongoDB Storage**: Uses MongoDB for users, bots, and settings.

## 🛠️ Tech Stack

- **Runtime**: Node.js
- **Backend**: Express.js
- **Bot Framework**: Mineflayer
- **Frontend**: EJS + Tailwind CSS (CDN)
- **Real-time**: Socket.io
- **Auth**: express-session + bcrypt (MongoDB storage)

## 📋 Prerequisites

- Node.js (v16 or higher recommended)
- npm (Node Package Manager)

## 📦 Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/shotxd01/shotdevs_mc_project.git
   cd shotdevs_mc_project
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the application:**
   ```bash
   npm start
   ```
   The dashboard will be available at `http://localhost:3010` by default.

## 🔐 Default Login

- **Username**: `root`
- **Password**: `@el@12`

> **Note**: You can change the password by updating the Admin record in MongoDB (requires hashing the new password) or implementing a change password feature.

## ⚙️ Environment Variables

- `MONGODB_URI`: MongoDB connection string (required in production).
- `SESSION_SECRET`: Session signing secret (required in production).
- `NODE_ENV`: Set to `production` to enable secure session cookies.
- `TRUST_PROXY`: Set to `true` or `1` when running behind a reverse proxy (Nginx, Render, etc.).
- `PORT`: Override the default port (3010).

## 🎮 Usage Guide

### 1. Initial Setup
- Log in to the dashboard.
- Go to the **Server** page.
- Enter the Minecraft Server IP, Port, and Version.
- Enter your Microsoft Account Email.
- Click "Save Changes".

### 2. Starting the Bot
- Go to the **Dashboard**.
- Click **Start Bot**.
- Watch the **Console** page or the status indicators.
- **First Time Login**: You will see a "Microsoft Authentication Required" modal.
  - Copy the code provided.
  - Click the link to open Microsoft Login.
  - Paste the code and authorize.
  - The bot should connect automatically after verification.

### 3. AFK Mode
- Click **Toggle AFK** on the dashboard to make the bot look around and jump randomly.

### 4. Console
- Use the **Console** page to view chat logs and send commands (start with `/`) or chat messages.

## 📂 Folder Structure

```
afk-bot-dashboard/
├── bot/
│   └── bot.js          # Mineflayer bot logic
├── data/
│   └── ...             # Runtime bot cache/history files
├── public/
│   └── js/
│       └── dashboard.js # Frontend logic
├── routes/             # Express routes
├── views/              # EJS templates
├── utils/              # Helper functions
└── app.js              # Main entry point
```

## ⚠️ Troubleshooting

- **Bot won't connect?** Check the Server IP and Port. Ensure the server is online and not whitelisted.
- **Microsoft Auth Loop?** If the bot keeps asking for auth, ensure you complete the flow on the Microsoft website. The token is cached in `data/nmp-cache` (managed by mineflayer).
- **Port in use?** If port 3000 is taken, change `PORT` in `app.js` or set `PORT` environment variable.

## 📜 License

ISC
