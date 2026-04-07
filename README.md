# Vmrestarts-Tools


This tool is designed to check the vm status of supplied vmnames in the input file as.txt

With these tool able to  do the following things

1.Checked the vm status of supplied list of vm from the vcenter
2.Can able to shutdown the VM list 
3.Can able to power on the vm list
4.Can able to  restart the vm list.

Pre requesties
1.Ensure the vm name supplied over .txt format is exact the vm name from the vcenter console, advice to grab the details directly from the vcenter,
2.As the Tool designed to use single user credentials supplied for the tool for vcenter login is not masked,ensure the credentials  privacy while executing the tool in meeting.
3.Can supply any vcenter login url ,ensure proper VMware connectivity from the designed systems and proper Powershell cmdlets be installed.

#To install the Vcenter PowerCLI

Install-Module VMware.VimAutomation.Core
Import-Module VMware.VimAutomation.Core
Set-ExecutionPolicy -ExecutionPolicy Unrestricted
Set-PowerCLIConfiguration -Scope User -ParticipateInCEIP $true

4.The Tools have designed to intiate the command as by line by line,as it be require press enter key in each run.

*This is set as it is ensure to avoid the  massive power on off all vms supplied in txt  and can control over the power on activity if any error came ,it be directly noted down and later trouble shoot.

5.Need to categories the vm and grouped into seperate txt files as App,DB SQL,Infra servers  and supplied into the  Tool.
6.The Tool can be run from multiple devices with same  vcenter operations as able to cordinate few more Users are engaged in Activity to reduce the Operational Time.


Prerequisites & Usage Guidelines
===========================================


VM Name Accuracy

VM names provided in the .txt file must exactly match the VM names in the vCenter console.
It is strongly recommended to copy VM names directly from vCenter to avoid naming mismatches.

Credential Handling

The tool uses a single set of vCenter credentials for login, and credentials are not masked during execution.
Please ensure credential confidentiality, especially when executing the tool during meetings or screen-sharing sessions.

Connectivity & Environment Requirements

Any valid vCenter login URL can be supplied.
Ensure proper VMware connectivity from the execution system.
Required VMware PowerShell cmdlets (PowerCLI) must be installed and properly configured.

Execution Methodology

The tool processes VMs line by line and requires manual confirmation (Enter key) for each operation.
This design is intentional to prevent accidental bulk power on/off of all VMs.
If an error occurs during execution, it is immediately visible, allowing it to be noted and troubleshooted before proceeding further.


VM Categorization & Input Structure

VM Grouping

VMs must be categorized and maintained in separate .txt files based on server role, such as:

Application Servers
Database / SQL Servers
Infrastructure Servers

Each group-specific .txt file can be independently supplied to the tool, enabling controlled and phased execution.


Multi-User & Parallel Execution

Distributed Execution Model

The tool can be executed from multiple systems using the same vCenter environment.
This allows multiple users to coordinate and work in parallel on different VM groups, thereby reducing overall operational time while maintaining execution control.
