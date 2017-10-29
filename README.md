# Introduction

The MSGraphIntuneManagement PowerShell module contains commands for working with the Microsoft Graph Intune API.

Optimally, we would use an official PowerShell module from Microsoft for this task. However, such module does not exist as of October 2017. There is a UserVoice suggestion called *[Add PowerShell support to manage the service](https://microsoftintune.uservoice.com/forums/291681-ideas/suggestions/8363319-add-powershell-support-to-manage-the-service)* which has 773 votes as of this writing, and a lot of comments from people wanting this.

In the mean time, this module is meant to bridge the gap and be a starting point for those who want to use PowerShell to administer the Intune service. Intially, only a few commands is added based on the authors need, but the hope is to get more people involved and extend it further.

# Installation

The module is published to the PowerShell Gallery, which means you can install it using the following command from the PowerShellGet module:

`Install-Module -Name MSGraphIntuneManagement`

or the following if you want it installed the current users profile (*$env:userprofile\Documents\WindowsPowerShell\Modules*) rather than the system wide location (*$env:programfiles\WindowsPowerShell\Modules*):

`Install-Module -Name MSGraphIntuneManagement -Scope CurrentUser`

When a new version is released with bug fixes or new functionality you can update to the latest version simply by typing the following command:

`Update-Module -Name MSGraphIntuneManagement`

PowerShellGet is included by default in PowerShell V5, and available downlevel for PowerShell 3.0 and 4.0.

If you want to install the module without leveraging PowerShellGet, you can either clone the Git-repository or download [this](https://github.com/janegilring/MSGraphIntuneManagement/archive/master.zip) ZIP-file and place the contains in one of the following locations:
- $env:userprofile\Documents\WindowsPowerShell\Modules\MSGraphIntuneManagement
- $env:programfiles\WindowsPowerShell\Modules\MSGraphIntuneManagement

# Requirements

- PowerShell 3.0 or later on the computer the module is installed on
- The AzureAD PowerShell module
    - Can be installed by running Install-Module -Name AzureAD

# Usage

After installation, you can view available commands by using Get-Command:
`Get-Command -Module MSGraphIntuneManagement`

The module currently contains the following functions:
- **Get-MSGraphAuthenticationToken** - This function is used to get an authentication token for the Graph API REST interface
- **Get-MSGraphAzureADUser** - This function is used to get Azure AD Users from the Graph API REST interface
- **Get-MSGraphIntuneUserDevice** - This function is used to get an Azure AD User Devices from the Graph API REST interface
- **Invoke-MSGraphIntuneDeviceAction** - This function is used to invoke actions against Intune devices from the Graph API REST interface

# Planned features and todo-list

- Add Pester tests
- Add additional commands based on the [PowerShell Intune Samples](https://github.com/microsoftgraph/powershell-intune-samples) from Microsoft


# Contributors

[Jan Egil Ring](https://twitter.com/JanEgilRing) - author

Everyone is welcome to assist by forking the project and submitting pull requests with proposed fixes and enhancements.
