# Project 5: Recovering and Analyzing Deleted Files on Windows Systems

## Introduction
Deleted files can still contain valuable information for forensic investigations. Recovering and analyzing these files can provide critical evidence of user activities or malicious actions. This project will guide you through the process of recovering and analyzing deleted files on Windows systems using various forensic tools.

## Lab Setup
To complete this project, you will need access to a Windows operating system. You can use a physical machine or set up a virtual machine using software like VirtualBox or VMware.

### Pre-requisites
- Basic understanding of Windows OS
- Familiarity with command-line interface
- Administrative privileges on the Windows machine

### Tools Installation
For this project, we will use the following tools:
1. **Recuva**: A tool for recovering deleted files.
2. **FTK Imager**: A forensic imaging tool.
3. **Autopsy**: A digital forensics platform and graphical interface to The Sleuth Kit.

#### Installing Recuva
1. Download Recuva from the [official website](https://www.ccleaner.com/recuva).
2. Run the installer and follow the on-screen instructions.

#### Installing FTK Imager
1. Download FTK Imager from the [AccessData website](https://accessdata.com/product-download).
2. Run the installer and follow the on-screen instructions.

#### Installing Autopsy
1. Download Autopsy from the [official website](https://www.sleuthkit.org/autopsy/).
2. Run the installer and follow the on-screen instructions.

## Exercises

### Exercise 1: Recovering Deleted Files using Recuva
**Objective**: Learn how to recover deleted files using Recuva.

**Steps**:
1. Open Recuva.
2. Select the type of files you want to recover (e.g., All Files).
3. Choose the location to scan for deleted files (e.g., a specific drive or folder).
4. Start the scan and wait for it to complete.
5. Review the list of recoverable files and select the ones you want to recover.
6. Click on `Recover` and choose a location to save the recovered files.

**Expected Output**: You should be able to recover deleted files and save them to your specified location.

### Exercise 2: Creating a Forensic Image of the Disk using FTK Imager
**Objective**: Learn how to create a forensic image of a disk for detailed analysis.

**Steps**:
1. Open FTK Imager.
2. Select `File` > `Create Disk Image`.
3. Choose the source type (e.g., Physical Drive) and select the drive you want to image.
4. Follow the prompts to create an image file (e.g., E01 format) and save it to your desired location.

**Expected Output**: You should have a forensic image of the selected disk saved in your specified location.

### Exercise 3: Analyzing Deleted Files using Autopsy
**Objective**: Use Autopsy to analyze the forensic image and recover deleted files.

**Steps**:
1. Open Autopsy and create a new case.
2. Add the forensic image created in Exercise 2 as a data source.
3. Navigate to the `File Analysis` module.
4. Filter the files to show only deleted files.
5. Review the list of deleted files and examine their contents.

**Expected Output**: You should be able to analyze and view the contents of deleted files using Autopsy.

### Exercise 4: Examining Metadata of Recovered Files
**Objective**: Extract and analyze metadata of recovered files to gather additional information.

**Steps**:
1. In Autopsy, locate the recovered files.
2. Right-click on a file and select `Extract File Metadata`.
3. Review the extracted metadata, including creation, modification, and access times, as well as file size and type.

**Expected Output**: You should be able to view and interpret the metadata of recovered files, providing additional context for the forensic investigation.

### Exercise 5: Correlating Recovered Files with System Events
**Objective**: Correlate recovered files with system events to understand the context of their deletion.

**Steps**:
1. In Autopsy, examine the timeline of system events around the time the files were deleted.
2. Look for events such as file creation, modification, and deletion, as well as user login and application execution.
3. Correlate these events with the recovered files to understand the context and reasons behind their deletion.
4. Document your findings and provide recommendations for further investigation.

**Expected Output**: You should be able to correlate recovered files with system events, providing a comprehensive understanding of the context and reasons behind their deletion.

---

With these exercises, you will gain practical experience in recovering and analyzing deleted files on Windows systems. This will enhance your skills in digital forensics and help you effectively investigate security incidents by uncovering valuable evidence from deleted files.
