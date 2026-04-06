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
