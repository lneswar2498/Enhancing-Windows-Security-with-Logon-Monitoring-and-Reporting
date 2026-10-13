# Enhancing-Windows-Security-with-Logon-Monitoring-and-Reporting
Deployed Windows in a virtualized lab environment and configured the system to support security monitoring and reporting. Prepared the necessary Windows settings, logging capabilities, and monitoring components to collect the security-related events. The project focused on event monitoring, and security reporting in a controlled lab environment.

Project Overview
================

In this project, I set up a Windows Server virtual machine and configured it to monitor security-related activities, especially user logon events.

The main idea was to understand how Windows records security events, how auditing policies can be configured, and how PowerShell can be used to collect and generate reports from those events.

I also worked with Windows Event Viewer, Group Policy, IIS Web Server, and Windows Firewall to create a basic security monitoring and reporting environment.

Tools and Technologies Used

Oracle VirtualBox

Windows Server 2022

Microsoft Management Console (MMC)

Local Group Policy Editor

Windows Event Viewer

Windows PowerShell and PowerShell ISE

Internet Information Services (IIS)

Windows Defender Firewall

Project Implementation
=======================

STEP-1:- Setting Up the Windows Environment
------
I started by setting up a Windows Server virtual machine in VirtualBox. Once the installation was complete, I logged into Windows and prepared the environment for security monitoring.

STEP-2:- Opening Microsoft Management Console
------
I opened the Run dialog and entered mmc to launch Microsoft Management Console.

From there, I added the Group Policy Object Editor snap-in and selected Local Computer Policy to access the security configuration settings.

STEP-3:- Navigating to Advanced Audit Policy Configuration
------
After opening Local Computer Policy, I followed this path:

Computer Configuration → Windows Settings → Security Settings → Advanced Audit Policy Configuration → System Audit Policies.

This section contains different auditing categories that help Windows record security-related activities.

STEP-4:- Configuring Account Logon Auditing
------
I started with the Account Logon category and configured the required auditing subcategories, including Credential Validation and Other Account Logon Events.

I enabled Success and Failure auditing for the selected settings to capture relevant authentication activities.

STEP-5:- Configuring Additional Security Audit Policies
------
Next, I worked with other auditing categories, including:

Detailed Tracking

Logon/Logoff

Object Access

Privilege Use

System

I configured relevant subcategories such as Process Creation, Logon, Special Logon, Registry, and System Events.

These settings helped increase the visibility of security-related activities on the Windows machine.

STEP-6:- Configuring File System Auditing
------
I moved to Global Object Access Auditing and configured the File System auditing settings.

I created an auditing entry using the Everyone principal and selected the required auditing permissions.

The purpose was to configure auditing for file system activities in the lab environment.

STEP-7:- Configuring PowerShell Logging
------
After completing the auditing policies, I moved to the Windows PowerShell settings under Administrative Templates.

I configured the script execution policy and enabled PowerShell Module Logging.

This was done to support PowerShell-based monitoring and provide additional visibility into script activity.

STEP-8:- Applying Group Policy Changes
------
Once the required configurations were completed, I restarted the Windows machine.

I then opened PowerShell and executed:

gpupdate /force

This command refreshes Group Policy settings so that the configured policies are applied.

STEP-9:- Monitoring Security Events Using Event Viewer
-------
After applying the policies, I opened Windows Event Viewer and navigated to:

Windows Logs → Security

I explored the recorded security events and used the Filter Current Log option to search for specific Event IDs.

For example, I examined Event ID 4689, which represents process termination.

This helped me understand how Windows records system activities and how individual events can be inspected.

STEP-10:- Collecting Security Events Using PowerShell
-------
Next, I used Windows PowerShell ISE to work with security event logs.

I created and executed PowerShell commands using Get-WinEvent to retrieve Windows Security log entries.

I also worked on filtering events and displaying their details, rather than checking every event manually through Event Viewer.

STEP-11:- Creating a PowerShell Script for Logon Information
-------
I saved a PowerShell script named login_info.ps1 to work with Windows logon information.

After restarting the machine, I executed the script again and checked the recorded events.

This helped me understand how PowerShell scripts can simplify security event monitoring.

STEP-12:- Installing and Configuring IIS Web Server
------
To support browser-based reporting, I opened Server Manager and added the Web Server (IIS) role.

I selected the required IIS components and .NET Framework features and completed the installation.

The purpose of this setup was to provide a web environment for displaying the generated security report.

STEP-13:- Configuring Windows Firewall
-------
After setting up IIS, I created a port-based inbound firewall rule for TCP port 8080.

I selected Allow the Connection and named the rule Allow 8080.

This was part of configuring network access for the lab environment.

STEP-14:- Generating and Viewing the Security Report
-------
Finally, I worked with a PowerShell reporting script named reports.ps1.

The script retrieved Windows Security log information and exported the results into an HTML report.

I then opened the generated report through a web browser and viewed the collected security event information in tabular format.

This completed the monitoring and reporting workflow.

Project Outcome
================
Through this project, I gained practical experience in configuring Windows auditing policies, monitoring security events, and working with PowerShell to retrieve and report event log information.

I also learned how different Windows components, including Group Policy, Event Viewer, IIS, and Windows Firewall, can be used together in a basic security monitoring environment.
