# Multisynq-node

# Install NVM (Node Version Manager)

![Copy me](https://img.shields.io/badge/copy-this--command-blue) curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

Setelah selesai, jalankan:

export NVM_DIR="$HOME/.nvm" && . "$NVM_DIR/nvm.sh"

# Install Node.js LTS
nvm install --lts     # atau bisa juga: nvm install 20
nvm use --lts

Pastikan Node dan NPM sudah terpasang:

node -v

npm -v

# Install Synqchronizer
npm install -g synqchronizer

# Jalankan Synqchronizer
synqchronizer init

Masukkan nama node anda , multisynq key anda dan alamat wallet anda

# Jalankan node
synqchronizer start

full details : https://www.npmjs.com/package/synqchronizer



