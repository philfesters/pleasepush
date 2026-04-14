# 🎵 pleasepush

> *"I used to drop bars on a beat. Now I push them to `main`."*  
> — **Grant Fezzy Festers**, Ravensmead, Cape Town 🇿🇦

[

![SSH](https://img.shields.io/badge/Auth-SSH%20Only-ff5500?style=flat-square&logo=openssh)

](https://github.com/settings/keys)
[

![Termux](https://img.shields.io/badge/Built%20From-Android%20+%20Termux-black?style=flat-square)

](https://termux.dev)
[

![Brand](https://img.shields.io/badge/Brand-Strategy%20Over%20Impulse-8800ff?style=flat-square)

](https://github.com/philfesters)
[

![License](https://img.shields.io/badge/License-MIT-00e676?style=flat-square)

](./LICENSE)

---

## 👤 The Creator

**Grant Phil Festers** — self-taught developer, content creator, and former rapper turned repo builder.  
No IDE. No laptop. No formal training. Just Termux on an Android phone and the philosophy of
**Strategy Over Impulse**.

I started on a mic spitting bars. Now I commit them. The hustle is the same — the syntax just changed.

And then there's **Bojack** 🐺 — a Lab/Husky mix, unofficial mascot, and head of **Bojack Security™**.  
He doesn't guard the house. He guards the SSH keys.  
Weak key? He finds it. He chews it. He doesn't even bury it — he leaves it in plain sight as a warning to other devs.

> *"I've seen devs commit their private keys to public repos. I watched their careers die in real time.*  
> *I didn't even bark. Some lessons need to land on their own."*  
> — Bojack, Security Daemon 💀

📧 **Email:** philfesters@gmail.com  
📱 **WhatsApp:** [+27 73 930 1858](https://wa.me/270739301858) *(WhatsApp only)*  
📘 **Facebook:** [Grant Fezzy Festers](https://www.facebook.com/search/top?q=Grant+Fezzy+Festers)  
🐙 **GitHub:** [github.com/philfesters](https://github.com/philfesters)

---

## 🔥 What Is `pleasepush`?

This repo is your **zero-password, fully SSH-powered guide** to linking Termux on Android to GitHub.  
Push, pull, and clone like a seasoned dev — without ever seeing a password prompt.

**The selling line:**

> 📌 Set up SSH once. Clone anything. Push everything.  
> **No password. No friction. Pure flow. Forever.**

---

## ⚡ Clone This Repo

### 🔑 SSH — Recommended (Zero Password)

```bash
git clone git@github.com:philfesters/pleasepush.git
🔗 HTTPS — Alternative (Requires Token)
git clone https://github.com/philfesters/pleasepush.git
SSH is the move. If you haven't set it up — that's literally what this repo exists for. Keep reading.
📁 What's Inside
pleasepush/
├── index.html     ← Full interactive guide (SoundCloud-themed, PDF generator included)
├── README.md      ← You're reading it
├── LICENSE        ← MIT
└── .gitignore
🚀 Complete SSH + Termux Setup — Step by Step
1️⃣ Install Git & OpenSSH
pkg update && pkg upgrade -y
pkg install git openssh -y
2️⃣ Generate Your SSH Key
ssh-keygen -t ed25519 -C "philfesters@gmail.com"
Press Enter 3 times. Accept defaults. No passphrase needed.
3️⃣ View Your Public Key
cat ~/.ssh/id_ed25519.pub
4️⃣ Copy Key to Clipboard (Termux)
cat ~/.ssh/id_ed25519.pub | termux-clipboard-set
📋 Paste Rules — Critical — Read Before Pasting:
Copy the entire key including ssh-ed25519 at the start
Include the email address at the end
No extra spaces. No line breaks. One single line.
GitHub rejecting it? Strip newlines first:
cat ~/.ssh/id_ed25519.pub | tr -d '\n' | termux-clipboard-set
5️⃣ Add Key to GitHub
Go to github.com/settings/keys
→ New SSH key → Authentication Key → Paste → Add SSH key
6️⃣ Test the Connection
ssh -T git@github.com
✅ Expected: Hi philfesters! You've successfully authenticated, but GitHub does not provide shell access.
7️⃣ Configure Git Identity
git config --global user.name "philfesters"
git config --global user.email "philfesters@gmail.com"
📤 Push a Repo from Termux
# Create & initialize
mkdir myrepo && cd myrepo
git init
git branch -M main

# Add files & commit
echo "# My Repo" > README.md
git add .
git commit -m "first push 🔥"

# Link to GitHub via SSH (no password)
git remote add origin git@github.com:philfesters/REPONAME.git

# Push
git push -u origin main
After that first push, every future update is just:
git add . && git commit -m "update" && git push
🛠️ Troubleshooting
Error
Fix
Permission denied (publickey)
Key not on GitHub or pasted wrong. Re-add at github.com/settings/keys
Host key verification failed
ssh-keyscan github.com >> ~/.ssh/known_hosts
remote: Repository not found
Check git remote -v — must be SSH URL not HTTPS
fatal: not a git repository
Run git init or cd to correct folder
Updates were rejected
git pull origin main --rebase then git push
Connection refused port 22
ssh -T -p 443 git@ssh.github.com
Key is invalid on GitHub
cat ~/.ssh/id_ed25519.pub | tr -d '\n' | termux-clipboard-set
src refspec main does not match any
Make a commit first before pushing
🚫 SSH Rules — What NOT To Do
"Bojack has seen things. Don't be those devs." 🐺
🚫 NEVER share your private key (~/.ssh/id_ed25519 — the one without .pub) with anyone, anywhere
🚫 NEVER commit your .ssh/ folder to any repo
🚫 NEVER reuse SSH keys across untrusted devices
🚫 NEVER store your private key outside ~/.ssh in plain text
🚫 NEVER use RSA 1024-bit — use ed25519 or rsa 4096 minimum
🚫 NEVER ignore unknown host warnings — could be a MITM attack
✅ DO revoke unused keys at github.com/settings/keys
📄 PDF Guide
Open index.html in any browser → click "Download PDF Guide" — it generates and downloads automatically. No server needed. Works offline.
📜 License
MIT — see LICENSE
�

Grant Phil Festers
Self-Taught Developer · Former Rapper · Content Creator
Ravensmead, Cape Town 🇿🇦
Strategy Over Impulse · 999 · Bojack Security™
GitHub · Email · WhatsApp · Facebook
Built from an Android phone. Pushed with SSH. No password. No excuses.
�
```