# ue4cleaner
Adds two options to the explorer context menu for .uproject to delete intermediate and binaries for the project and optionally the plugins, as well as the .sln. Then generates new project files.

## Installation
To install, grab the latest precompiled binary from https://github.com/Vaei/ue4cleaner/tree/master/Binaries
Then run the MSI installer.

Currently tested on Windows 10 only. Linux/OSX unsupported.

## Compiling Source & Generating Binaries
If you can use a precompiled binary, do that instead. If you want to make changes or compile for unsupported OS then continue.

To modify the source, simply open in Visual Studio 2017.

### Installer
WiX installer is used. Grab it here http://wixtoolset.org/releases/
WiX is used to add registry keys for the context menu and generate a convenient .msi that will install to a specified location as well as handling registration with the windows installer service (it will be in add/remove programs).

#### Usage
The simplest way to generate an installer is to go to the WIX bin folder (usually C:\Program Files (x86)\WiX Toolset v3.11\bin)
Then place the UE4CleanerInstaller.xml there along with the built UE4Cleaner.exe then run the two commands:

```
candle.exe UE4CleanerInstaller.xml
light.exe -ext WixUIExtension UE4CleanerInstaller.wixobj
```
