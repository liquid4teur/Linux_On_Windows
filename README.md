# Linux_On_Windows

Before installing a Linux distribution, you have to activate the WSL (Windows Subsystem for Linux) function on Windows 10. Launch a PowerShell session as administrator and execute the following command:

>dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

Now, you have to update the WSL to WSL 2 (in order to enable the latest functionnalities). To do so, we enable the Virtual Machine Platform feature:

>dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

Then, we allow WSL 2 to be the default version used:

>wsl --set-default-version 2

On the Microsoft Store, you can download a Linux distribution (Ubuntu on my case). After downloading it, launch it (this may take a few minutes). You'll have to configure a UNIX username and password.

# Adding it to Windows Terminal

I personnally installed the new Windows Terminal. This terminal allows to add an Ubuntu Tab directly onto the terminal. On the Ubuntu version you installed from the Microsoft Store, copy the unique GUID number by doing (on the Ubuntu machine):

>uuidgen

Now open the settings on the Windows Terminal and add a profile:

```
{
    "guid": "{THE_UNIQUE_GUID_NUMBER}",
    "name": "Ubuntu 20.04",
    "commandline": "wsl.exe -d Ubuntu-20.04"

}
```
# Ressources 

[Installation](https://docs.microsoft.com/fr-fr/windows/wsl/install-win10#install-your-linux-distribution-of-choice)
[Windows Terminal Customization](https://docs.microsoft.com/fr-fr/windows/terminal/customize-settings/profile-settings)