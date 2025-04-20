# 🚀 Gensyn Node Guide

This guide will walk you through the setup process for running a Gensyn node on your VPS.

---

## 🛠️ Installation Steps

```bash
# Step 1: Create and enter the Gensyn directory
mkdir Gensyn
cd Gensyn

# Step 2: Update system and install required packages
apt update && apt install -y sudo

sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof && \
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - && \
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list && \
sudo apt update && sudo apt install -y yarn

# Step 3: Download and run the Gensyn installation script
curl -sSL https://raw.githubusercontent.com/zunxbt/installation/main/node.sh | bash

# Step 4: Start a screen session for running the node
screen -S gensyn

# Step 5: Setup Python virtual environment and start the node
python3 -m venv .venv && . .venv/bin/activate && ./run_rl_swarm.sh
