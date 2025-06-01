![image](https://github.com/user-attachments/assets/8ad5a694-e287-4d45-ba57-203f58a19714)




Step1 - Open ubntu & old users backup or copy your swarm.pem file using this cmd.

Copy command 👇

1- Create Directory - 
```bash 
mkdir swarm.backup
```

2- Copy swarm file- 
```bash  
cp rl-swarm/swarm.pem swarm.backup
```


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

## 1) Install Dependencies
**1. Update System Packages**
```bash
sudo apt-get update && sudo apt-get upgrade -y
```
**2. Install General Utilities and Tools**
```bash
sudo apt install screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y
```

**3. Install Docker**
```bash
# Remove old Docker installations
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

# Add Docker repository
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Install Docker
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Test Docker
sudo docker run hello-world
```
* Tip: To run Docker without sudo, add your user to the Docker group:
```bash
sudo usermod -aG docker $USER
```

**4. Install Python**
```bash
sudo apt-get install python3 python3-pip python3-venv python3-dev -y
```

**5. Install Node**
```
sudo apt-get update
```
```
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
```
```
sudo apt-get install -y nodejs
```
```
node -v
```
```bash
sudo npm install -g yarn
```
```bash
yarn -v
```

**6. Install Yarn**
```bash
curl -o- -L https://yarnpkg.com/install.sh | bash
```
```bash
export PATH="$HOME/.yarn/bin:$HOME/.config/yarn/global/node_modules/.bin:$PATH"
```
```bash
source ~/.bashrc
```

---

## 2) Get HuggingFace Access token
**1- Create account in [HuggingFace](https://huggingface.co/)**

**2- Create an Access Token with `Write` permissions [here](https://huggingface.co/settings/tokens) and save it**

---

## 3) Clone the Repository
```bash
git clone https://github.com/gensyn-ai/rl-swarm/
cd rl-swarm
```

---

## 4) Run the swarm
Open a screen to run it in background
```bash
screen -S swarm
```
Install swarm
```bash
python3 -m venv .venv
source .venv/bin/activate
./run_rl_swarm.sh
```
Press `Y`

---

## 5) Login
**1- You have to receive `Waiting for userData.json to be created...` in logs**

![image](https://github.com/user-attachments/assets/140f7d32-844f-4cf0-aac4-a91e9a14c1aa)

**2- Open login page in browser**
* Local PC: `http://localhost:3000/`
* VPS: `http://ServerIP:3000/`

**3- If you can't login via VPS then, Forward port**
* In windows start menu, Search **Powershell** and open its terminal in your local PC
* Enter the command below and replace your vps ip with `Server_IP` and your vps port(.eg 22) with `SSH_PORT`
```
ssh -L 3000:localhost:3000 root@Server_IP -p SSH_PORT
```
* This prompts you to enter your VPS password, when you enter it, you connect and tunnel to your vps
* Now go to browser and open `http://localhost:3000/` and login

**4- Login with your preferred method**

![image](https://github.com/user-attachments/assets/f33ea530-b15f-4af7-a317-93acd8618a9f)

* After login, your terminal starts installation.

**5- Push models to huggingface**
* Enter your HuggingFace access token you've created when it prompted

![image](https://github.com/user-attachments/assets/11c3a798-49c2-4a87-9e0b-359f3378c9e2)

---

## 6) Backup
**1- Node name**
* Now your node started running, Find your name after word `Hello`, like mine is `whistling hulking armadillo` as in the image below (You can use `CTRL+SHIFT+F` to search Hello in terminal)

![image](https://github.com/user-attachments/assets/a1abdb1a-aa11-407f-8e5b-abe7d0a6b0f3)

**2- Node `.pem` file**
* Save `swarm.pem` file in this directory: `/root/rl-swarm/`

---

### Screen commands
* Minimize: `CTRL` + `A` + `D`
* Return: `screen -r swarm`
* Stop and Kill: `screen -XS swarm quit`

---

## 7) Run Swarm Dashboard UI (Optional)
```bash
cd $HOME cd rl-swarm
```
```bash
docker compose up -d --build
```
Open the dashboard in browser via:
* Local PC: `0.0.0.0:8080`
* VPS: `ServerIP:8080`

---

* Official dashboard: https://dashboard.gensyn.ai/

**You can search your Node name in the dashboard after a while when you have done your first training completed**

![image](https://github.com/user-attachments/assets/cd8e8cd3-f057-450a-b1a2-a90ca10aa3a6)

---
# Run on Hyperbolic GPUs
* To install the node on **Hyperbolic** check this [Guide: Rent & Connect to GPU](https://github.com/0xmoei/Hyperbolic-GPU)
* Add this flag: `-L 3000:localhost:3000` in front of your Hyperbolic's `SSH-command`, this will allow you to access to login page via local system.

![Screenshot_677](https://github.com/user-attachments/assets/ea4fc4c1-0993-4fa5-b573-33f256bc639b)
