# Installation Instructions

## Prerequisites

- Windows 10 or later
- PowerShell or Command Prompt
- Visual Studio 2017 (required for compatibility)
- Approximately 10+ GB of disk space for all required tools

## Steps to Install Build Tools

1. **Install Visual Studio Build Tools 2022:**

   ```powershell
   winget install Microsoft.VisualStudio.2022.BuildTools
   ```

2. **Install the C++ Build Workload:**

   - Open the Visual Studio Installer (search for "Visual Studio Installer" in the Start menu).
   - Find "Visual Studio Build Tools 2022" and click "Modify".
   - In the Workloads tab, check "Desktop development with C++".
   - In the Individual components tab, search for and select:
     - Windows 10 SDK (10.0.16299.0)
   - Click "Modify" at the bottom right to install the workload and components.

3. **Build the Project:**
   - Open a new terminal (to ensure environment variables are refreshed).
   - Run the following command to build for x64:
     ```powershell
     & "C:\Program Files (x86)\Microsoft Visual Studio\2022\BuildTools\MSBuild\Current\Bin\MSBuild.exe" .\Source\SDK-CPP.sln /p:Configuration=Release /p:Platform=x64
     ```

## Troubleshooting

- If `msbuild` is not recognized, ensure the Build Tools are installed correctly and the path is added to your system's PATH environment variable.
- If the build fails with missing C++ files, ensure the "Desktop development with C++" workload is installed.
- If you get an error about Windows SDK version 10.0.16299.0, make sure to install it from the Individual components tab in Visual Studio Installer.
- Ensure Visual Studio 2017 is installed for compatibility with the project.
- Note: The total installation size for all required tools is over 10 GB.
