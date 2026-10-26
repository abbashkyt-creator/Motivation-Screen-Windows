# Motivation Screen - Windows Installer

**Your screen works for your goals - even when you are away.**

Motivation Screen plays your motivational videos on the screen when you step away, and gets out of the way the moment you come back. It watches folders you choose, stops for apps and quiet hours, can show a goal and quotes between videos, and has a built-in downloader.

| File | Size | SHA-256 |
|---|---|---|
| `MotivationScreen.msi` (1.0.0) | 487,424 bytes | `1F28307EA205210D69BD95BE458C1F8FE5B7AC592431553D5FA96D3FE69EB3C3` |
| `MotivationScreen-1.0.0-portable.zip` | 637,022 bytes | `A9B08093FFB76CAA10BD41E8B29DB1CBD7938020664925629A6B79F5A408DEE9` |

## Requirements

- Windows 10 or Windows 11 (x64)
- **.NET 8 Desktop Runtime**: https://dotnet.microsoft.com/download/dotnet/8.0
- Microsoft Edge **WebView2 Runtime** (already included with Windows 11)

## Install with the MSI

1. Download `MotivationScreen.msi`.
2. Double-click it. Windows SmartScreen warns because the package is not Authenticode-signed - choose **More info -> Run anyway**.
3. Accept the UAC prompt (it installs to `C:\Program Files\Motivation Screen`).
4. Two Start Menu entries appear:
   - **Motivation Screen** - the settings window
   - **Motivate me now** - play the screen immediately
5. Uninstall any time from *Settings > Apps > Installed apps*.

## Run the portable build

1. Download `MotivationScreen-1.0.0-portable.zip` and extract it anywhere.
2. Double-click `MotivationScreen.exe` (settings) or `MotivationScreen.exe --play`.

No administrator rights and nothing written to Program Files.

## What is in the settings window

- **Add your first motivation videos** - the folders it watches for video files
- **When it starts** - idle time, and the apps it must not start over ("Don't start when")
- **Quiet hours** - the hours it stays off
- **Sound & playback** - volume, muting, and what happens when you come back
- **Goal & quotes** - your goal on screen and quotes between videos
- **Downloads** - the built-in downloader
- **Accounts**
- **Shortcut & app** - the keys while videos play, and About

## Verify a download

```powershell
Get-FileHash .\MotivationScreen.msi -Algorithm SHA256
Get-FileHash .\MotivationScreen-1.0.0-portable.zip -Algorithm SHA256
```

Compare against the table above.

## Notes

- Neither artifact is Authenticode-signed, so SmartScreen warns on first run; the hash table is the integrity check.
- Settings, logs and the WebView2 cache live under `%LocalAppData%\MotivationScreen`, separate from the program files.

## Source

The application source is not published in this repository. This repository carries the installers only.

## License

All rights reserved. This is **not** an MIT-licensed project and no open-source license is granted for the application, the MSI or the portable build. You may download and install them for personal use. Redistribution, modification or republishing is not permitted.