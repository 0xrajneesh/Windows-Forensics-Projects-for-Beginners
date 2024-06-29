# Project 1: Investigating Windows Event Logs for Security Incidents

## Introduction
Windows Event Logs are a crucial source of information for identifying and investigating security incidents. This project will guide you through the process of analyzing Windows Event Logs to detect potential security threats. You will learn how to access, interpret, and utilize these logs to identify suspicious activities and mitigate risks.

## Lab Setup
To complete this project, you will need access to a Windows operating system. You can use a physical machine or set up a virtual machine using software like VirtualBox or VMware.

### Pre-requisites
- Basic understanding of Windows OS
- Familiarity with command-line interface
- Administrative privileges on the Windows machine

### Tools Installation
For this project, we will use the following tools:
1. **Event Viewer**: A built-in Windows tool for viewing event logs.
2. **PowerShell**: A command-line shell and scripting language for Windows.
3. **Log Parser**: A versatile tool from Microsoft for parsing event logs.

#### Installing Log Parser
1. Download Log Parser from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=24659).
2. Run the installer and follow the on-screen instructions.

## Exercises

### Exercise 1: Accessing Windows Event Logs using Event Viewer
**Objective**: Learn how to access and navigate through Windows Event Logs using Event Viewer.

**Steps**:
1. Open Event Viewer:
   - Press `Win + R`, type `eventvwr.msc`, and press `Enter`.
2. Navigate through different log categories:
   - Expand `Windows Logs` to see Application, Security, Setup, System, and Forwarded Events logs.
3. Explore the Security log to identify login attempts:
   - Click on `Security` under `Windows Logs`.
   - Review the events for any suspicious login attempts.

**Expected Output**: You should be able to see and navigate through various event logs, identifying different types of events, particularly in the Security log.

### Exercise 2: Filtering and Exporting Event Logs
**Objective**: Learn how to filter and export event logs for detailed analysis.

**Steps**:
1. Open Event Viewer and select the `Security` log.
2. Apply a filter to show only failed login attempts:
   - Right-click on `Security` and select `Filter Current Log`.
   - In the filter window, select `Event ID` and enter `4625`.
   - Click `OK` to apply the filter.
3. Export the filtered logs:
   - Right-click on the filtered logs and select `Save Filtered Log File As`.
   - Save the file as `FailedLogins.evtx`.

**Expected Output**: You should be able to filter the event logs for specific event IDs and export the filtered logs to a file.

### Exercise 3: Parsing Event Logs using Log Parser
**Objective**: Use Log Parser to extract and analyze data from event logs.

**Steps**:
1. Open Command Prompt and navigate to the Log Parser installation directory.
2. Run the following command to extract information from the `FailedLogins.evtx` file:
   ```sh
   LogParser.exe "SELECT TimeGenerated, EventID, EventTypeName, Message INTO FailedLogins.csv FROM FailedLogins.evtx" -i:EVT -o:CSV
   ```

3. Open the FailedLogins.csv file to review the extracted data.

**Expected Output**: You should have a CSV file containing detailed information about the failed login attempts.

### Exercise 4: Analyzing Event Logs using PowerShell
Objective: Use PowerShell to automate the analysis of Windows Event Logs.

Steps:

1. Open PowerShell with administrative privileges.
2. Run the following command to list failed login attempts:
```powershell
Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4625} | Format-Table TimeCreated, Id, Message -AutoSize
```
3. Save the output to a text file for further analysis:
```powershell
Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4625} | Format-Table TimeCreated, Id, Message -AutoSize | Out-File -FilePath FailedLogins.txt
```
**Expected Output**: You should see a list of failed login attempts in the PowerShell console and have the output saved to a text file.

### Exercise 5: Correlating Events for Comprehensive Analysis
Objective: Correlate different event logs to identify potential security incidents.

**Steps**:

1. Open Event Viewer and select the Security log.
2. Identify events related to successful logins (Event ID: 4624) and compare them with failed login attempts (Event ID: 4625).
3. Use Log Parser to correlate these events:
```sh
LogParser.exe "SELECT a.TimeGenerated AS FailedLoginTime, b.TimeGenerated AS SuccessfulLoginTime, a.Message AS FailedLoginMessage, b.Message AS
SuccessfulLoginMessage INTO CorrelatedLogins.csv FROM FailedLogins.evtx a JOIN SuccessfulLogins.evtx b ON a.User=b.User WHERE a.EventID=4625 AND b.EventID=4624" -i:EVT -o:CSV
```
4. Review the CorrelatedLogins.csv file to identify any patterns or anomalies.
**Expected Output**: You should be able to correlate failed and successful login attempts, providing a comprehensive view of potential security incidents.

With these exercises, you will gain practical experience in investigating Windows Event Logs for security incidents, leveraging both built-in tools and additional utilities to enhance your analysis capabilities.
