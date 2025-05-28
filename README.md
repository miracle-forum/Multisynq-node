# Multisynq Node Setup Guide

# Docker Installation Tutorial on Ubuntu

A quick step-by-step guide to install Docker and Docker Compose Plugin on Ubuntu to get you started with containers.

---

## Step 1: Update and Install Dependencies

```bash
sudo apt-get update -y
sudo apt-get install -y ca-certificates curl gnupg lsb-release

Add Docker's Official GPG Key and Repository
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

Install Docker and Docker Compose Plugin

sudo apt-get update -y
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

Verify Docker Installation

sudo docker run hello-world



🟦 Install NVM (Node Version Manager)
<pre> <code id="code1">curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash</code> <button onclick="copy('code1')"></button> </pre>
Once installed, run the following:

<pre> <code id="code2">export NVM_DIR="$HOME/.nvm" && . "$NVM_DIR/nvm.sh"</code> <button onclick="copy('code2')"></button> </pre>
🟩 Install Node.js LTS
<pre> <code id="code3">nvm install --lts # or: nvm install 20 nvm use --lts</code> <button onclick="copy('code3')"></button> </pre>
✅ Check Node and NPM
<pre> <code id="code4">node -v npm -v</code> <button onclick="copy('code4')"></button> </pre>
📦 Install Synqchronizer CLI
<pre> <code id="code5">npm install -g synqchronizer</code> <button onclick="copy('code5')"></button> </pre>
⚙️ Initialize the Synqchronizer
<pre> <code id="code6">synqchronize init</code> <button onclick="copy('code6')"></button> </pre>
📝 Enter your node name, Multisynq key, and wallet address when prompted.

▶️ Start the Synchronizer Node
<pre> <code id="code7">synqchronize start</code> <button onclick="copy('code7')"></button> </pre>

🛠️ Synchronizer Systemd Service (One-Liner)
Run the following command to generate and start the systemd service in one go:

<pre> <code id="code9">synqchronize service && sudo cp ~/.synqchronize/synqchronize.service /etc/systemd/system/ && sudo systemctl daemon-reload && sudo systemctl enable synqchronize && sudo systemctl start synqchronize</code> <button onclick="copy('code9')"></button> </pre>
💡 This command generates the systemd service file, copies it to the proper directory, reloads systemd, enables the service at boot, and starts it immediately.

# Access Web Dashboard ( optional )

synchronize web

dashboard access : http://<YOUR_VPS_IP>:3000

# Monitoring status & points

synchronize status
synchronize points








📖 Full Documentation
https://www.npmjs.com/package/synqchronizer





