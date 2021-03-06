<p align="center">
    <a href="https://www.powershellgallery.com/packages/AsBuiltReport.VMware.NSXv/" alt="PowerShell Gallery Version">
        <img src="https://img.shields.io/powershellgallery/v/AsBuiltReport.VMware.NSXv.svg" /></a>
    <a href="https://www.powershellgallery.com/packages/AsBuiltReport.VMware.NSXv/" alt="PS Gallery Downloads">
        <img src="https://img.shields.io/powershellgallery/dt/AsBuiltReport.VMware.NSXv.svg" /></a>
    <a href="https://www.powershellgallery.com/packages/AsBuiltReport.VMware.NSXv/" alt="PS Platform">
        <img src="https://img.shields.io/powershellgallery/p/AsBuiltReport.VMware.NSXv.svg" /></a>
</p>
<p align="center">
    <a href="https://github.com/AsBuiltReport/AsBuiltReport.VMware.NSXv/graphs/commit-activity" alt="GitHub Last Commit">
        <img src="https://img.shields.io/github/last-commit/AsBuiltReport/AsBuiltReport.VMware.NSXv/master.svg" /></a>
    <a href="https://raw.githubusercontent.com/AsBuiltReport/AsBuiltReport.VMware.NSXv/master/LICENSE" alt="GitHub License">
        <img src="https://img.shields.io/github/license/AsBuiltReport/AsBuiltReport.VMware.NSXv.svg" /></a>
    <a href="https://github.com/AsBuiltReport/AsBuiltReport.VMware.NSXv/graphs/contributors" alt="GitHub Contributors">
        <img src="https://img.shields.io/github/contributors/AsBuiltReport/AsBuiltReport.VMware.NSXv.svg"/></a>
</p>
<p align="center">
    <a href="https://twitter.com/AsBuiltReport" alt="Twitter">
            <img src="https://img.shields.io/twitter/follow/AsBuiltReport.svg?style=social"/></a>
</p>

# VMware NSX-v AsBuiltReport

The VMware NSX-v AsBuiltReport is a module of the parent "AsBuiltReport" [project](https://github.com/AsBuiltReport/AsBuiltReport). AsBuiltReport is a PowerShell module which generates As-Built documentation for many common datacentre infrastructure systems. Reports can be generated in Text, XML, HTML and MS Word formats and can be presented with custom styling to align with your company/customer's brand.

For detailed documentation around the whole project, please refer to the `README.md` file in the parent AsBuiltReport repository (linked to above). This README is specific only to the VMware NSX-v repository.

# Sample Reports

## Sample Report 1 - Default Style
Sample NSX-v As Built report using default report style.

![Sample vSphere Report 1](https://github.com/AsBuiltReport/AsBuiltReport.VMware.NSXv/blob/master/Samples/Sample_NSXv_Report_1.png "Sample NSX-v Report 1")

## Sample Report 2 - Custom Style
Sample NSX-v As Built report using custom report style.

![Sample vSphere Report 2](https://github.com/AsBuiltReport/AsBuiltReport.VMware.NSXv/blob/master/Samples/Sample_NSXv_Report_2.png "Sample NSX-v Report 2")

# Getting Started

Below are the instructions on how to install, configure and generate a VMware NSX-v As Built Report

## Pre-requisites
The following PowerShell modules are required for generating a VMware NSX-v As Built report.

Each of these modules can be easily downloaded and installed via the PowerShell Gallery 

- [VMware PowerCLI Module](https://www.powershellgallery.com/packages/VMware.PowerCLI/)
- [PowerNSX Module](https://www.powershellgallery.com/packages/PowerNSX/)
- [AsBuiltReport Module](https://www.powershellgallery.com/packages/AsBuiltReport/)

### Module Installation

Open a Windows PowerShell terminal window and install each of the required modules as follows;
```powershell
Install-Module VMware.PowerCLI
Install-Module PowerNSX
Install-Module AsBuiltReport
```

### Required Privileges

To generate a VMware NSX-v report, a user account with the administrator role or higher to the target vCenter Server and Enterprise Administrator on the target NSX Manager is required.

## Configuration

The VMware NSX-v As Built Report utilises a JSON file to allow configuration of report information, options, detail and healthchecks.

A VMware NSX-v report configuration file can be generated by executing the following command;
```powershell
New-AsBuiltReportConfig -Report VMware.NSXv -Path <User specified folder> -Name <Optional>
```

Executing this command will copy the default NSX-v report JSON configuration to a user specified folder.

All report settings can then be configured via the JSON file.

The following provides information of how to configure each schema within the report's JSON file.

<Placeholder for future - there are currently no configurable options for the VMware NSX-v Report>


## Examples
There is one example listed below on running the AsBuiltReport script against a vCenter Server target which will report on the NSX environment registered with the specified vCenter Server.

- The following creates a VMware NSXv As-Built report in HTML & Word formats and exports the report to the C:\scripts folder
```powershell
PS C:\>New-AsBuiltReport -Report VMware.NSXv -Target vc01 -Credential (Get-Credential) -Format HTML,Word -OutputPath C:\Scripts
```

## Known Issues
