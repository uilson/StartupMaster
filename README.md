# StartupMaster - Windows Startup Sequence & Application Manager

**StartupMaster** is a native, modern desktop application built with **C# (.NET 9.0)** and **WPF** featuring a Windows 11 Fluent Design interface (via Lepo WPF-UI). It provides precise control over which programs start when Windows boots, what order they initialize in, custom delay intervals between launches, and full settings configuration.

---

## 🌟 Key Features

### 1. 🚀 Ordered Startup Sequence & Timing Controls
- **Order of Initialization**: Move programs up or down (`#1`, `#2`, `#3`, ...) to ensure dependencies initialize in the exact sequence you want (e.g., VPN -> Database -> Discord -> Browser).
- **Per-App Delay Timers**: Set custom pause times (e.g., wait 3 seconds before starting the next app) to prevent CPU/Disk bottlenecks during boot.
- **Granular Controls**:
  - Enable / Disable individual apps without deleting them.
  - Option to **Run as Administrator** (`runas`).
  - Option to **Launch Minimized** (`ProcessWindowStyle.Minimized`).
  - Command-line arguments & custom working directory support.
  - **Test Launch**: Launch any individual program on-demand with one click.
  - **Live Execution Progress**: Watch real-time second-by-second countdowns and status indicators for each item.

### 2. 📦 Installed Programs Auto-Discovery
- Automatically scans your system:
  - 64-bit and 32-bit Windows Registry (`HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall`).
  - Current User Registry (`HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall`).
  - Common & User Start Menu Shortcuts (`C:\ProgramData` and `%AppData%`).
- Filters out uninstallers, helpers, and internal updates.
- Real-time search filter (e.g., search "Steam", "Spotify", "Chrome").
- **One-Click Add**: Click **Add to Startup** directly from the installed apps catalog.
- High-resolution icon extraction from executables and shortcuts.

### 3. ⚙️ App Settings & Windows Integration
- **Start with Windows Toggle**: Directly registers/unregisters StartupMaster in Windows Registry (`HKCU\Software\Microsoft\Windows\CurrentVersion\Run`).
- **Start up Minimized**: Open the app window minimized to the taskbar at Windows startup.
- **Start Minimized to System Tray**: Hide the window at Windows startup and keep the app available from the system tray.
- **Auto-Launch Sequence on Boot**: Automatically trigger program launches upon system logon.
- **Boot Countdown Safety Delay**: Customizable countdown (e.g., 5 seconds) allowing you to cancel or pause the sequence before apps launch.
- **Default Delay Timer**: Configure global default pause between apps (1-60s).
- **Minimize to Tray on Minimize**: Clicking the minimize button hides the window to the system tray.
- **Minimize to Tray on Close**: Closing the window (`X`) minimizes it to the system tray so it keeps running.
- **Windows Notification Balloons**: Receive alerts when all startup programs have completed launching.
- **Appearance**: Toggle between Dark and Light Fluent themes.

### 4. 🗂 System Tray Integration
- Resides in the Windows Taskbar Notification Area (System Tray).
- Double-click to restore the main window.
- Right-click context menu:
  - *Open StartupMaster*
  - *Run Startup Sequence Now*
  - *Exit*

---

## 🚀 How to Run & Build

### Running in Development Mode
```powershell
cd "C:\StartupMaster"
dotnet run
```

### Building for Release
```powershell
dotnet build -c Release
```
Executable is created at:
`bin\Release\net9.0-windows\StartupMaster.exe`
