# 🛰️ Multisynq Node Setup Guide

This guide walks you through setting up a Multisynq Synchronizer node using Docker, Node.js, and the `synqchronizer` CLI tool on an Ubuntu server.

---

# 🐳 Docker Installation on Ubuntu

A quick step-by-step guide to install Docker and Docker Compose Plugin.

---

## Step 1: Update and Install Dependencies

```bash
sudo apt-get update -y
sudo apt-get install -y ca-certificates curl gnupg lsb-release
```

---

## Step 2: Add Docker's Official GPG Key and Repository

```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

---

## Step 3: Install Docker and Docker Compose Plugin

```bash
sudo apt-get update -y
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

---

## Step 4: Verify Docker Installation

```bash
sudo docker run hello-world
```

If you see a "Hello from Docker!" message, you're good to go!

---

## 🟦 Install NVM (Node Version Manager)

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

Once installed, run:

```bash
export NVM_DIR="$HOME/.nvm" && . "$NVM_DIR/nvm.sh"
```

---

## 🟩 Install Node.js LTS

```bash
nvm install --lts
nvm use --lts
```

---

## ✅ Check Node and NPM

```bash
node -v
npm -v
```

---

## 📦 Install Synqchronizer CLI

```bash
npm install -g synqchronizer
```

---

## ⚙️ Initialize the Synqchronizer

```bash
synchronize init

```

Fill in your node name, Multisynq key, and wallet address when prompted.

---

## ▶️ Start the Synchronizer Node

```bash
synchronize start

```

---

## 🛠️ Create a Systemd Service for Synqchronizer (One-liner)

```bash
  Start service:    sudo systemctl start synchronizer-cli
  Stop service:     sudo systemctl stop synchronizer-cli
  Restart service:  sudo systemctl restart synchronizer-cli
  Enable auto-start: sudo systemctl enable synchronizer-cli
  View live logs:   journalctl -u synchronizer-cli -f
  View all logs:    journalctl -u synchronizer-cli

```

This command will generate the systemd service file, install it, and start the synchronizer automatically.

---

## 🌐 Access Web Dashboard 

```bash
synchronize web
```

Then open in browser: `http://<YOUR_VPS_IP>:3000`

---

## 📊 Monitor Status & Points

```bash
synchronize status
synchronize points

```

---

## 📖 Full Documentation

You can find the full documentation at:  
[https://www.npmjs.com/package/synqchronizer](https://www.npmjs.com/package/synqchronizer)

https://github.com/multisynq/synchronizer-cli





