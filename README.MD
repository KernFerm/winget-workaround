# Manual PATH Setup for winget 🚀

Many users have experienced issues where **winget** (the Windows Package Manager) isn’t recognized in the command line—even though it’s installed via the Microsoft Store. This guide will walk you through adding winget to your system’s PATH manually.

---

## Why You Usually Don’t Need to Do This 🤔

**winget** is normally installed as part of the App Installer package from the Microsoft Store. It automatically creates a symlink in your user’s `%LOCALAPPDATA%\Microsoft\WindowsApps` folder, and Windows adds that folder to your PATH. In most cases, you can run `winget` from any terminal without extra work. If that isn’t happening, follow these steps!

---

## Steps to Manually Add winget to Your PATH 🔧

### 1. Locate `winget.exe` 🔍
- %LOCALAPPDATA%\Microsoft\WindowsApps
- Where To `copy` & `paste`
**copy this below and paste it in the location where it says `Home` in the image.**
```
%LOCALAPPDATA%\Microsoft\WindowsApps
```
<p align="left">
  <img src="https://github.com/KernFerm/winget-workaround/blob/main/image.png" width="500" alt="image">
</p>


- Find the full path to `winget.exe`. It might look something like:

```
C:\Users<YourUserName>\AppData\Local\Microsoft\WindowsApps\Microsoft.DesktopAppInstaller_8wekyb3d8bbwe\winget.exe
```

*Tip:* You only need the folder path (without `\winget.exe` at the end).

---

### 2. Open Environment Variables ⚙️

- Press **Win + R**, type `SystemPropertiesAdvanced`, and press **Enter**.
- In the **System Properties** window, click on **Environment Variables…**.

---

### 3. Edit the PATH Variable 📝

- Under **System variables**, select **Path** and click **Edit**.
- Click **New**, then paste the folder path (remember, without `\winget.exe`):

```
C:\Users<YourUserName>\AppData\Local\Microsoft\WindowsApps\Microsoft.DesktopAppInstaller_8wekyb3d8bbwe
```

- Click **OK** to save your changes and close all dialog boxes.

---

### 4. Restart Your Terminal 🔄

Close and reopen Command Prompt, PowerShell, or Windows Terminal so that the updated PATH is recognized.

---

### 5. Verify the Setup ✅

Open a new terminal window and run:
```shell
winget --version
```

- You should see the winget version displayed, confirming that everything is working!

Troubleshooting 🤷‍♂️

Double-check the path: Make sure the folder path is correct.
Restart your terminal: Sometimes a full restart of your shell or computer is needed.
Error messages: If you run into issues, look for error details and search for help online.

Note: Manual PATH updates are typically not required because the App Installer handles this automatically. This guide is a workaround for those encountering issues with winget not being recognized.
