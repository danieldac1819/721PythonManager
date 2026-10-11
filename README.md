# 721 Python Manager

**721 Python Manager** is a Windows desktop application for finding Python installations, inspecting Python scripts and managing their dependencies from one place.

Copyright © 2026 721PC-Net Corporation.
<img width="480" height="475" alt="image" src="https://github.com/user-attachments/assets/e060b521-ad80-4b59-8e42-492fff6514b2" />

## Features

- Detect Python environments and show their executable, pip executable, version and architecture.
- Open `.py` and `.pyw` files with the file picker, drag and drop, command line, or the Windows **Edit with IDLE → 721 Detect Module** context menu.
- View Python source code with syntax highlighting and identify imported packages that are missing from the selected environment.
- Install missing packages in a batch, review installed packages, and uninstall selected packages.
- Run scripts and commands against the selected Python environment.
- Use command presets for Nuitka, PyInstaller, cx_Freeze and Briefcase.
- Browse current Python releases from Python.org and download or install available Windows x86 and x64 packages.
- View operating system and device architecture information.
- Reopen recently used scripts from a scrollable **Recent Files** panel. The history is limited to 50 files and is stored in `%ProgramData%\721PythonManager.ini`.

## Download and run

Download the complete distribution from the project's GitHub Releases. Keep the launcher and both architecture folders together:

```text
dist/
├── 721PythonManager.exe       # Shared launcher
├── win-x86/
│   ├── 721_win-x86.exe
│   └── ...                    # x86 application and .NET runtime files
└── win-x64/
    ├── 721_win-x64.exe
    └── ...                    # x64 application and .NET runtime files
```

Run `721PythonManager.exe`. It selects the matching x86 or x64 application for the current Windows installation. The distribution is self-contained and does not require a separate .NET runtime installation. Keep all files and folders in the distribution; the architecture folders contain required application and runtime files.

Python itself is only needed for running scripts and managing Python packages. The manager can also be opened before Python is installed, for example to browse Python releases.

## Open a script from the command line

Pass a script path directly:

```powershell
.\721PythonManager.exe "C:\Scripts\example.py"
```

Or specify the script and Python executable explicitly:

```powershell
.\721PythonManager.exe --open-script "C:\Scripts\example.py" --python "C:\Python313\python.exe"
```

The application also accepts `.pyw` files. When registered, **721 Detect Module** is added inside Python's existing **Edit with IDLE** context-menu entry. Registration is available when a Python environment is detected and can be toggled from the application.

## Python downloads

Release and Windows installer metadata is read from Python.org's public JSON indexes. Downloaded packages are saved in a `Download_Version` folder next to the shared launcher. When automatic installation is enabled, the manager runs the official installer with the selected architecture and destination folder.

## Technology

- C# and Windows Forms
- .NET 8 (`net8.0-windows`)

## Copyright

Copyright © 2026 721PC-Net Corporation. No license file is currently included in this repository; add the project's chosen license before redistributing the source under open-source terms.
