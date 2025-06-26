![image](https://github.com/Harkesh8171/Image/blob/main/IMG_8122.jpg))


# Run RL Swarm (Testnet) Node
RL Swarm is a fully open-source framework developed by GensynAI for building reinforcement learning (RL) training swarms over the internet. This guide walks you through setting up an RL Swarm node and a web UI dashboard to monitor swarm activity.

## Hardware Requirements
- CPU: Minimum 16GB RAM (more RAM recommended for larger models or datasets).

OR

- GPU (Optional): Supported CUDA devices for enhanced performance:
    - RTX 3090
    - RTX 4090
    - A100
    - H100
-  **Note**: You can run the node without a GPU using CPU-only mode.

---

## 1) Open a ubntu create new directory & old users backup or copy your swarm.pem file using this cmd.

**1. Create Directory**
```bash
mkdir swarm.backup
```
**2. Copy swarm.pem file to another directory**
```bash
cp rl-swarm/swarm.pem swarm.backup
```

**3. Delete Old rl-swarm folder**
```bash 
rm-rf rl-swarm
```

**4. Install Pyton & Yarn**
```bash
sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - && echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list && sudo apt update && sudo apt install -y yarn
```

**5. Intall Node.JS**
```bash
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install -y nodejs
```
**6. Delete Old Python venv**
```bash
rm -rf .venv
```
Activate New Python venv
```bash
python3 -m venv .venv
source .venv/bin/activate
```
**7. Clone Swarn**
```bash
git clone https://github.com/gensyn-ai/rl-swarm.git
cd rl-swarm
```

**8. Run with CPU using this CMD**
```bash
CPU_ONLY=true ./run_rl_swarm.sh
```

**Run With GPU CMD**
```bash
./run_rl_swarm.sh
```

# Open next ubntu window and download ngork with key 

**9- Install Ngork**
```bash
wget https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz && tar -xvzf ngrok-v3-stable-linux-amd64.tgz && sudo mv ngrok /usr/local/bin/
```

** visit: https://ngrok.com
- Sign up using email
- Go to Your Authtoken Section
- Click on "show authtoken" 
- Copy that command
- Go back paste and run the command
— next run this **

**10- Connect With Ngork**
```bash
ngrok http 3000
```

**11- Copied your .free address & open your chrome browser**

- Sign up using email
- Enter OTP
- Done & check your key has been activated



# Mac Users

**1. Install Pyton & Yarn**
```bash
brew install python
```

**2. Install Yarn & Node.Js**
```bash
brew install node && corepack enable && npm install -g yarn
```

**3. Delete Old Python venv**
```bash
rm -rf .venv
```
Activate New Python venv
```bash
python3 -m venv .venv
source .venv/bin/activate
```
**4. Clone Swarn**
```bash
git clone https://github.com/gensyn-ai/rl-swarm.git
cd rl-swarm
```

**5. Run with CPU using this CMD**
```bash
CPU_ONLY=true ./run_rl_swarm.sh
```

**Run With GPU CMD**
```bash
./run_rl_swarm.sh
```

# Open next ubntu window and download ngork with key 

**6- Install Ngork**
```bash
wget https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz && tar -xvzf ngrok-v3-stable-linux-amd64.tgz && sudo mv ngrok /usr/local/bin/
```

** visit: https://ngrok.com
- Sign up using email
- Go to Your Authtoken Section
- Click on "show authtoken" 
- Copy that command
- Go back paste and run the command
— next run this **

**7- Connect With Ngork**
```bash
ngrok http 3000
```

**8- Copied your .free address & open your chrome browser**

- Sign up using email
- Enter OTP
- Done & check your key has been activated


# Please Backup Your Swarm.Pem file in your PC 🖥

Using this cmd👇
```bash
[ -f backup.sh ] && rm backup.sh; curl -sSL -O https://raw.githubusercontent.com/zunxbt/gensyn-testnet/main/backup.sh && chmod +x backup.sh && ./backup.sh
```

