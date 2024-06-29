# Project 3: Forensic Analysis of Windows File Systems and Artifacts

## Introduction
Windows file systems and artifacts contain valuable information that can be crucial during forensic investigations. This project will guide you through the process of analyzing Windows file systems and extracting important artifacts using various forensic tools. You will learn how to identify and interpret key artifacts to uncover potential security incidents.

## Lab Setup
To complete this project, you will need access to a Windows operating system. You can use a physical machine or set up a virtual machine using software like VirtualBox or VMware.

### Pre-requisites
- Basic understanding of Windows OS
- Familiarity with command-line interface
- Administrative privileges on the Windows machine

### Tools Installation
For this project, we will use the following tools:
1. **FTK Imager**: A forensic imaging tool.
2. **Autopsy**: A digital forensics platform and graphical interface to The Sleuth Kit.
3. **Windows File Analyzer**: A tool to analyze various Windows artifacts.

#### Installing FTK Imager
1. Download FTK Imager from the [AccessData website](https://accessdata.com/product-download).
2. Run the installer and follow the on-screen instructions.

#### Installing Autopsy
1. Download Autopsy from the [official website](https://www.sleuthkit.org/autopsy/).
2. Run the installer and follow the on-screen instructions.

#### Installing Windows File Analyzer
1. Download Windows File Analyzer from the [official website](http://www.mitec.cz/wfa.html).
2. Run the installer and follow the on-screen instructions.

## Exercises

### Exercise 1: Creating a Forensic Image using FTK Imager
**Objective**: Learn how to create a forensic image of a disk using FTK Imager.

**Steps**:
1. Open FTK Imager.
2. Select `File` > `Create Disk Image`.
3. Choose the source type (e.g., Physical Drive) and select the drive you want to image.
4. Follow the prompts to create an image file (e.g., E01 format) and save it to your desired location.

**Expected Output**: You should have a forensic image of the selected disk saved in your specified location.

### Exercise 2: Analyzing File System with Autopsy
**Objective**: Use Autopsy to analyze the file system of the forensic image created in Exercise 1.

**Steps**:
1. Open Autopsy and create a new case.
2. Add the forensic image created in Exercise 1 as a data source.
3. Navigate through the file system hierarchy in Autopsy.
4. Identify and examine key directories such as `Users`, `Program Files`, and `Windows`.

**Expected Output**: You should be able to navigate through the file system and identify key directories and files.

### Exercise 3: Extracting and Analyzing MFT (Master File Table)
**Objective**: Extract and analyze the Master File Table (MFT) to identify file creation, modification, and deletion activities.

**Steps**:
1. In Autopsy, locate the `$MFT` file under the `NTFS` file system.
2. Extract the `$MFT` file to your local machine.
3. Use a tool like `MFTECmd` to parse the MFT:
   ```sh
   MFTECmd.exe -f <path_to_MFT> -o <output_directory>
Review the parsed MFT output to identify recent file activities.
Expected Output: You should have a parsed output of the MFT showing file creation, modification, and deletion activities.

### Exercise 4: Analyzing Windows Prefetch Files
Objective: Use Windows File Analyzer to analyze Prefetch files and identify recently executed applications.

**Steps**:

1. Open Windows File Analyzer.
2. Load the Prefetch files from the forensic image (usually located in C:\Windows\Prefetch).
3. Review the list of executed applications and their execution times.

**Expected Output**: You should be able to see a list of recently executed applications and their execution details.

### Exercise 5: Investigating Recent Activity using Shellbags
Objective: Analyze Shellbags to determine recently accessed directories and files.

**Steps**:

1. In Autopsy, locate and extract the NTUSER.DAT files for each user.
2. Use a tool like ShellBags Explorer to analyze the extracted NTUSER.DAT files:
```sh
SBECmd.exe -f <path_to_NTUSER.DAT> -o <output_directory>
```
3. Review the Shellbags analysis to identify recently accessed directories and files.

**Expected Output**: You should be able to identify recently accessed directories and files for each user.

With these exercises, you will gain practical experience in forensic analysis of Windows file systems and artifacts. This will enhance your skills in digital forensics and help you effectively investigate security incidents by uncovering valuable evidence.
