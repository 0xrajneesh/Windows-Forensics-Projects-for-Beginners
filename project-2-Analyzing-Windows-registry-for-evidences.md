# Project: Analyzing Windows Registry for Evidence of Malicious Activity

## Introduction
The Windows Registry is a critical hierarchical database that stores low-level settings for the operating system and installed applications. Analyzing the Windows Registry can reveal traces of malicious activity and provide valuable evidence during forensic investigations. This project will guide you through the process of using the Volatility tool to analyze Windows Registry hives and identify potential security incidents.

## Lab Setup
To complete this project, you will need access to a Windows operating system and a memory image for analysis. You can use a physical machine or set up a virtual machine using software like VirtualBox or VMware.

### Pre-requisites
- Basic understanding of Windows OS and the Windows Registry
- Familiarity with command-line interface
- Administrative privileges on the Windows machine

### Tools Installation
For this project, we will use the following tool:
1. **Volatility**: An advanced memory forensics framework.

#### Installing Volatility
1. Download Volatility from the [official website](https://www.volatilityfoundation.org/releases).
2. Extract the downloaded archive to a directory of your choice.
3. Ensure you have Python installed on your system. Volatility is compatible with Python 2.7.

## Exercises

### Exercise 1: Extracting Windows Registry Hives from a Memory Image
**Objective**: Learn how to extract Windows Registry hives from a memory image using Volatility.

**Steps**:
1. Open a command prompt and navigate to the Volatility installation directory.
2. Run the following command to list the available profiles in the memory image:
   ```sh
   volatility -f <memory_image> imageinfo
   ```
3. Extract the Windows Registry hives using the hivelist plugin:
```sh
volatility -f <memory_image> --profile=<profile> hivelist
```
4. Note the virtual addresses of the hives and dump them using the dumpregistry plugin:
```sh
volatility -f <memory_image> --profile=<profile> dumpregistry -o <virtual_address> -D <output_directory>
```
Expected Output: You should be able to extract the Windows Registry hives from the memory image and save them to your specified directory.

### Exercise 2: Analyzing the SAM Hive for User Information
Objective: Use Volatility to analyze the SAM hive and extract user account information.

Steps:

1. Ensure you have extracted the SAM hive from the memory image in Exercise 1.
2. Run the following command to parse the SAM hive and extract user account information:
```sh
volatility -f <memory_image> --profile=<profile> hashdump -y <system_hive> -s <sam_hive>
```
**Expected Output**: You should be able to view user account information, including username and hashed passwords.

### Exercise 3: Investigating Autorun Entries in the Software Hive
Objective: Identify potential autorun entries in the Software hive that could indicate malicious activity.

Steps:

1. Ensure you have extracted the Software hive from the memory image in Exercise 1.
2. Run the following command to analyze autorun entries:
```sh
volatility -f <memory_image> --profile=<profile> printkey -o <software_hive_virtual_address> -K "Microsoft\Windows\CurrentVersion\Run"
```

**Expected Output**: You should be able to identify any autorun entries in the Software hive, which could indicate potential malware persistence mechanisms.

### Exercise 4: Examining User Assist Keys in the NTUSER.DAT Hive
Objective: Analyze User Assist keys to determine recently accessed applications by a specific user.

**Steps**:

1. Ensure you have extracted the NTUSER.DAT hive from the memory image in Exercise 1.
2. Run the following command to list User Assist keys:
```sh
volatility -f <memory_image> --profile=<profile> userassist -i
```

**Expected Output**: You should be able to view a list of recently accessed applications and their execution counts, which can help identify suspicious activity.

### Exercise 5: Correlating Registry Artifacts for Comprehensive Analysis
Objective: Correlate information from different registry hives to gain a comprehensive understanding of potential malicious activity.

**Steps**:

1. Review the extracted data from previous exercises, including user account information, autorun entries, and User Assist keys.
2. Identify any patterns or correlations that could indicate a security incident.
3. Document your findings and provide recommendations for further investigation or remediation.

Expected Output: You should be able to correlate registry artifacts and provide a detailed analysis of potential malicious activity, supporting your findings with evidence from the Windows Registry.

With these exercises, you will gain practical experience in analyzing the Windows Registry for evidence of malicious activity using the Volatility tool. This will enhance your skills in memory forensics and help you effectively investigate security incidents.
