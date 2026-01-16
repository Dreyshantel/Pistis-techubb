# System Installation and Documentation
This guide walks you step by step through setting up a full development workflow on Windows, starting from creating a GitHub account all the way to pushing your first Markdown file to a repository.

## Create a GitHub Account
1. Go to https://github.com
2. Click Sign up
3. Enter:
    - Email address
    - Password and username
4. Complete the verification steps
5. Choose the Free plan
6. verify email address

You now have a GitHub account.


## Install Chocolatey (Windows Package Manager)
Chocolatey is a window package manager that lets you install software from the command line.
Step 1: Open PowerShell as Administrator
1. Press Start
2. Type PowerShell
3. Right‑click Windows PowerShell → Run as administrator

## Step 2: Install Chocolatey
Copy and paste this command, then press Enter:

```
Set-ExecutionPolicy Bypass -Scope Process -Force; 
[System.Net.ServicePointManager]::SecurityProtocol = 
[System.Net.ServicePointManager]::SecurityProtocol -bor 3072; 
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```
<img width="1889" height="1032" alt="image" src="https://github.com/user-attachments/assets/ff5e5aa1-2e47-4e49-9f5d-c9003b240778" />


## Step 3: Verify Installation

```
choco --version
```
if you see version number chocolatey is installed


##  Install Windows Terminal
from the cli, install windows terminal using this command

```
choco install microsoft-windows-terminal -y
```
After installation Open Windows Terminal from the Start menu


## Install Git
Git is the version control system used by GitHub. Install Git using the following command:

```
choco install git -y
```

verify
```
git --version
```
<img width="1892" height="1046" alt="image" src="https://github.com/user-attachments/assets/bd4a3115-33eb-4375-9a87-12e58260dcc1" />


## Install Visual Studio Code (VS Code)
Visual studio code is an effective source code editor which is developed bt microsoft
install visual studio code using the following:

```
choco install vscode -y
```
After installation, Open VS Code from the Start menu.


## Install VS Code Extensions
Required Extensions
1. Open VS Code
2. Click the Extensions icon (left sidebar)
3. Install:
   - GitHub Pull Requests and Issues
   - Markdown All in One
  
<img width="1879" height="1010" alt="image" src="https://github.com/user-attachments/assets/9f3dc53c-bfbd-45e1-8e2d-34e77712c3e2" />
<img width="1896" height="1020" alt="image" src="https://github.com/user-attachments/assets/54cece8f-e337-4e21-874c-7945e6627fbd" />

Install OpenSSH using the follwing command:
```
choco install openssh -y
```

Check if SSH is already installed:

```
ssh -V
```


## Generate SSH Keys
This is guide on how to create a new ssh key
Step 1: Create a New SSH Key
   - Press Enter to accept the default file location
   - Enter a passphrase (recommended) or press Enter to skip
<img width="1904" height="741" alt="image" src="https://github.com/user-attachments/assets/b4b292a8-8d25-4e47-b2ea-27d484f3b761" />

Step 2: Confirm if ssh Files Exist
You should see id_ed25519 (private key) and id_ed25519.pub (public key)
```
ls ~/.ssh
```
<img width="791" height="352" alt="image" src="https://github.com/user-attachments/assets/beadcda7-f0bb-4820-9f4d-1882a97c5af4" />


**Start and Configure SSH Agent**
start ssh agent and add your key to the agent using the following:

```
Start-Service ssh-agent
ssh-add ~/.ssh/id_ed25519
ssh-add -l
```

<img width="1302" height="392" alt="image" src="https://github.com/user-attachments/assets/79879e42-8ef5-4ee5-a0c8-03d59e166642" />

**Add Your Public SSH Key to GitHub**
Step 1: Copy the Public Key using the concatenate command

```
cat ~/.ssh/id_ed25519.pub
```

Step 2: Add Key on GitHub
1. Go to GitHub → Profile picture → Settings
2. Click SSH and GPG keys
3. Click New SSH key
4. Title: My Windows PC
5. Paste the key
6. Click Add SSH key
<img width="1837" height="988" alt="image" src="https://github.com/user-attachments/assets/9a553e42-6a59-417c-8086-787dc7345622" />


Step 3: Test Connection
```
ssh -T git@github.com
```
you should see a success message
<img width="1213" height="215" alt="image" src="https://github.com/user-attachments/assets/7cfbba94-b3d2-43f7-b64e-c696a77f511c" />


## Create a Repository on GitHub
1. Go to GitHub
2. Click New repository
3. Repository name: my-first-repo
4. Set to Public or Private
5. Do NOT initialize with README
6. Click Create repository

<img width="1861" height="978" alt="image" src="https://github.com/user-attachments/assets/a342ffc8-c59c-471e-be67-5694011c0be2" />


## Clone the Repository
Copy the SSH URL from GitHub, then run:

```
https://github.com/Dreyshantel/Pistis-techub..git
```
<img width="1216" height="175" alt="image" src="https://github.com/user-attachments/assets/2d87a8c8-d5a6-4f1f-b8f7-28661cc6a323" />


##  Create a Markdown Document
Step 1: Create the File

```
code .
```
In VS Code:
1. Create a new file
2. Name it README.md
<img width="1895" height="1024" alt="image" src="https://github.com/user-attachments/assets/25825b39-d7c2-4f51-ae28-d1ccd12b4898" />


## Commit and Push Your Changes to GitHub
Step 1: Check your git Status

```
git status
```

Step 2: Add Files

```
git add .
```

Step 3: Commit changes

```
git commit -m "Add system installation and documentation file in README"
```

Step 4: Push to GitHub