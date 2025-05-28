# 🛰️ Multisynq Node Setup Guide

This guide walks you through setting up a Multisynq Synchronizer node using Docker, Node.js, and the `synqchronizer` CLI tool on an Ubuntu server.

---

## 🐳 Docker Installation on Ubuntu

A quick step-by-step guide to install Docker and Docker Compose Plugin.

### Step 1: Update and Install Dependencies

```bash
sudo apt-get update -y
sudo apt-get install -y ca-certificates curl gnupg lsb-release

### Step 2: Add Docker's Official GPG Key and Repository

sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

### Step 3: Install Docker and Docker Compose Plugin

sudo apt-get update -y
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

### Step 4: Verify Docker Installation

sudo docker run hello-world

If you see a "Hello from Docker!" message, you're good to go!



### 🟦 Install NVM (Node Version Manager)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

Then activate NVM:
export NVM_DIR="$HOME/.nvm" && . "$NVM_DIR/nvm.sh"

### 🟩 Install Node.js (LTS Version)

nvm install --lts
nvm use --lts

### ✅ Verify Node and NPM Installation
node -v
npm -v

### 📦 Install Synqchronizer CLI
npm install -g synqchronizer

### ⚙️ Initialize the Synchronizer

synqchronize init

📝 Enter your node name, Multisynq key, and wallet address when prompted.


### ▶️ Start the Synchronizer Node
synqchronize start

### 🛠️ Set Up as Systemd Service (One-Liner)
Run the following command to generate, install, and start the systemd service automatically:

synqchronize service && \
sudo cp ~/.synqchronize/synqchronize.service /etc/systemd/system/ && \
sudo systemctl daemon-reload && \
sudo systemctl enable synqchronize && \
sudo systemctl start synqchronize

### 🌐 Access Web Dashboard (Optional)

synqchronize web

Access it at: http://<YOUR_VPS_IP>:3000

### 📊 Monitor Status & Points
Check current status:
synqchronize status

Check earned points:
synqchronize points


### 📖 Full Documentation
You can find more information here:

🔗 https://www.npmjs.com/package/synqchronizer





