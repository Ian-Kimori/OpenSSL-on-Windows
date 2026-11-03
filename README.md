# OpenSSL-on-Windows

The quickest route is **winget**, which is built into Windows 10/11. Open PowerShell or Windows Terminal and run:

```powershell
winget install ShiningLight.OpenSSL.Light
```

(Use `ShiningLight.OpenSSL.Dev` instead if you also need headers and libs for compiling against OpenSSL.)

This installs to `C:\Program Files\OpenSSL-Win64\`. Winget doesn't always add it to PATH, so if `openssl` isn't recognized after you reopen the terminal, add it yourself:

```powershell
[Environment]::SetEnvironmentVariable("Path", $env:Path + ";C:\Program Files\OpenSSL-Win64\bin", "User")
```

Then open a new terminal and verify:

```powershell
openssl version
```

**Other options**

If you use Chocolatey, run `choco install openssl` from an admin shell. If you use Scoop, run `scoop install openssl` (no admin needed, and it handles PATH for you). If you just want the installer, Shining Light Productions (slproweb.com) provides the standard Win64 builds that winget pulls from.

**Already have it?** If Git for Windows is installed, it ships with OpenSSL at `C:\Program Files\Git\usr\bin\openssl.exe`, so you can use it from Git Bash right away or point to that path directly.
