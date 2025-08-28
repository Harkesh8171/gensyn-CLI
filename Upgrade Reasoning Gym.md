![image](https://github.com/Harkesh8171/Image/blob/c656fa326410d74858d9a96edc2bbc205c19f881/Screenshot%202025-08-28%20233616.png)


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
rm -rf rl-swarm
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

**12. Paste swarm.pem file to rl-swarm directory**
```bash
cp swarm.backup/swarm.pem rl-swarm
```

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


# New Error Coming On Gensyn Node

![image](https://github.com/Harkesh8171/Image/blob/89439ac1303fc7baae697e7b6a0921e004b2b53a/gensyn%20error.jpg)

**1 Activate New Python venv**

```bash
python3 -m venv .venv
source .venv/bin/activate
```
**2- Enter rl-swarm**

```bash
cd rl-swarm
```

**3- Reset and update files**

```bash
git switch main
git reset --hard
git clean -fd
git pull origin main
```
**4- Run Node**

```bash
./run_rl_swarm.sh
```



<div align="center">

# The Gswarm Role - Link TG Bot

</div>



Follow these instructions to set up a Swarm node monitoring Telegram bot and earn the Swarm Discord role

## Step 1. Install Gswarm
```bash
# Install Go:
sudo rm -rf /usr/local/go
curl -L https://go.dev/dl/go1.22.4.linux-amd64.tar.gz | sudo tar -xzf - -C /usr/local
echo 'export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin' >> $HOME/.bash_profile
echo 'export PATH=$PATH:$(go env GOPATH)/bin' >> $HOME/.bash_profile
source .bash_profile
go version
```
```
go install github.com/Deep-Commit/gswarm/cmd/gswarm@latest
```
After this, you can run `gswarm` from anywhere (if your Go bin directory is in your PATH).

### Verify Installation
```
gswarm --version
```

## Step 2. Setup Telegram Bot

**1. Create a Telegram Bot:**
* Chat with [@BotFather](https://t.me/botfather) on Telegram
* Send `/newbot` and follow the instructions (Choose a name & username)
* Save the bot token provided

 
**2. Get Your Chat ID:**
* Start a chat with your new bot and send some messages to it
* Visit `https://api.telegram.org/botYOUR_BOT_TOKEN/getUpdates` in your browser
  * Replace `<YOUR_BOT_TOKEN>` with your actual bot token.
  * Ensure the word `bot` remains in the URL before the token.
* Find your chat ID in the response
* Example: If your bot token is `1234567890:ABCdefGHIjklMNOpqrsTUVwxyz`, visit:
```
https://api.telegram.org/bot1234567890:ABCdefGHIjklMNOpqrsTUVwxyz/getUpdates
```


**Sample Response:**
```
{
  "ok": true,
  "result": [
    {
      "message": {
        "message_id": 2021,
        "from": {
          "id": 123456789,
          "is_bot": false,
          "first_name": "GSwarm",
          "username": "gswarm_user",
          "language_code": "en"
        },
        "chat": {
          "id": 123456789,
          "first_name": "GSwarm",
          "username": "gswarm_user",
          "type": "private"
        },
        "date": 1704067200,
        "text": "Hello bot!"
      }
    }
  ]
}
```
* **Extract the Chat ID**: Look for the `"chat":{"id":123456789}` field. In this example, the chat ID is `123456789`. This is your Telegram ID that the bot will use to send you notifications.

**Note:** If you get an empty result `{"ok":true,"result":[]}`, you may need to send a message to your bot first, then refresh the URL.


## Step 3. Run Gswarm Bot
Run `gswarm` in your terminal now and follow the prompts to enter your bot token, chat ID, and EOA address
* You'll find **EOA address**  by logging in the [Gensyn Dashboard](https://dashboard.gensyn.ai/)


## Step 4. Linking Discord and Telegram
To link your Discord and Telegram accounts:

**1. Get the verification code:**
* Go to Discord in `#|swarm-link` channel
* Type `/link-telegram` (this gives you a code)


**2. Verify the code:**
* Go to your Telegram bot
* Type `/verify <code>` (replace `<code>` with the code you received)

This will link your Discord and Telegram accounts and you earn **The Swarm** role.



# Please Backup Your Swarm.Pem file in your PC 🖥

Using this cmd👇
```bash
[ -f backup.sh ] && rm backup.sh; curl -sSL -O https://raw.githubusercontent.com/zunxbt/gensyn-testnet/main/backup.sh && chmod +x backup.sh && ./backup.sh
```

