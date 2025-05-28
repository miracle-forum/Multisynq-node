# Multisynq Node Setup Guide



🟦 Install NVM (Node Version Manager)
<pre> <code id="code1">curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash</code> <button onclick="copy('code1')"></button> </pre>
Once installed, run the following:

<pre> <code id="code2">export NVM_DIR="$HOME/.nvm" && . "$NVM_DIR/nvm.sh"</code> <button onclick="copy('code2')"></button> </pre>
🟩 Install Node.js LTS
<pre> <code id="code3">nvm install --lts # or: nvm install 20 nvm use --lts</code> <button onclick="copy('code3')"></button> </pre>
✅ Check Node and NPM
<pre> <code id="code4">node -v npm -v</code> <button onclick="copy('code4')">📋 Copy</button> </pre>
📦 Install Synqchronizer CLI
<pre> <code id="code5">npm install -g synqchronizer</code> <button onclick="copy('code5')"></button> </pre>
⚙️ Initialize the Synqchronizer
<pre> <code id="code6">synqchronizer init</code> <button onclick="copy('code6')"></button> </pre>
📝 Enter your node name, Multisynq key, and wallet address when prompted.

▶️ Start the Synchronizer Node
<pre> <code id="code7">synqchronizer start</code> <button onclick="copy('code7')"></button> </pre>

🛠️ Synchronizer Systemd Service
Generate and install the Synchronizer system service for auto-start on reboot:

<pre> <code id="code8">synqchronizer service sudo cp ~/.synqchronizer/synqchronizer.service /etc/systemd/system/ sudo systemctl daemon-reload sudo systemctl enable synqchronizer sudo systemctl start synqchronizer</code> <button onclick="copy('code8')"></button> </pre>


📖 Full Documentation
https://www.npmjs.com/package/synqchronizer





