# Hyper-ConvertImage

![PowerShell Gallery](https://img.shields.io/powershellgallery/v/Hyper-ConvertImage.svg?style=flat&logo=powershell&label=PSGallery%20Version)
![PSGallery Downloads](https://img.shields.io/powershellgallery/dt/Hyper-ConvertImage.svg?style=flat&logo=powershell&label=PSGallery%20Downloads)

Microsoft hasn't published any approved PRs on their [Convert-WindowsImage](https://github.com/MicrosoftDocs/Virtualization-Documentation/tree/master/hyperv-tools/Convert-WindowsImage) module in years. This is a more recent version.

## How to use

### Install the module

``` PowerShell
Install-Module Hyper-ConvertImage -Scope CurrentUser
```

### Standard Windows Image Conversion

``` PowerShell
$params = @{
    SourcePath = "C:\Path\To\Source.iso"
    Edition    = 1
    VhdType    = "Dynamic"
    VhdFormat  = "VHDX"
    VhdPath    = "C:\Path\To\output.vhdx"
    DiskLayout = "UEFI"
    SizeBytes  = 127gb
}
Convert-WindowsImage @params
```

### Windows Image Conversion w/ Unattend File

``` PowerShell
$params = @{
    SourcePath   = "C:\Path\To\Source.iso"
    Edition      = 1
    VhdType      = "Dynamic"
    VhdFormat    = "VHDX"
    VhdPath      = "C:\Path\To\output.vhdx"
    DiskLayout   = "UEFI"
    SizeBytes    = 127gb
    UnattendPath = "C:\Path\To\Unattend.xml"
}
Convert-WindowsImage @params
```