# Windows Portable build

This checkout contains the official DeepSeek Harness source plus `BUILD-WINDOWS-PORTABLE.cmd`.

## Requirements

- Windows 10/11 x64
- Node.js 22.19+ (or 24+)
- Internet access for npm/Electron dependencies
- PowerShell (included in modern Windows)

## Build

Double-click:

`BUILD-WINDOWS-PORTABLE.cmd`

The script installs the pinned pnpm version, builds the project, creates an **unsigned Windows x64 unpacked Electron application**, and packs it into:

`DeepSeek-Harness-Windows-x64-Portable.zip`

The resulting archive is portable: extract it and run `DeepSeek Harness.exe`.

### Important

This ZIP is a **Windows build bundle**, not the already compiled `.exe`. The current execution environment is Linux, while this repository's own packaging code explicitly requires a Windows x64 build host for `win-x64`, so the Windows-native packaging step must run on Windows.

The generated local build is unsigned. Windows SmartScreen may therefore show a warning.

Do not put a real `DEEPSEEK_API_KEY` into source control. Configure credentials only on the machine where you run the application.
