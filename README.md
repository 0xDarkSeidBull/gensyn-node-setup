# 🚀 Gensyn Node Guide

This guide will walk you through the setup process for running a Gensyn node on your VPS.

---

## 🛠️ Installation Steps
## 🧠 Gensyn Node Setup Guide

```bash
# 1. Create a directory and move into it
mkdir Gensyn
cd Gensyn

# 2. Update package list and install sudo
apt update && apt install -y sudo

# 3. Install required packages
sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof

# 4. Add Yarn APT repository and install it
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt update && sudo apt install -y yarn

# 5. Run the official Gensyn install script
curl -sSL https://raw.githubusercontent.com/zunxbt/installation/main/node.sh | bash

# 6. Start a new screen session named 'gensyn'
screen -S gensyn

# 7. Activate virtual environment and start the node
python3 -m venv .venv && . .venv/bin/activate && ./run_rl_swarm.sh
