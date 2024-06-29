# Project 4: Extracting and Interpreting Browser Artifacts on Windows

## Introduction
Web browsers store a wealth of information about user activities, including history, cookies, cache, and download records. Analyzing browser artifacts can provide critical evidence during forensic investigations. This project will guide you through the process of extracting and interpreting browser artifacts from popular web browsers on Windows.

## Lab Setup
To complete this project, you will need access to a Windows operating system. You can use a physical machine or set up a virtual machine using software like VirtualBox or VMware.

### Pre-requisites
- Basic understanding of Windows OS
- Familiarity with command-line interface
- Administrative privileges on the Windows machine

### Tools Installation
For this project, we will use the following tools:
1. **WebBrowserPassView**: A tool to recover passwords stored in web browsers.
2. **BrowserHistoryViewer**: A tool to view browser history from various web browsers.
3. **SQLite Database Browser**: A tool to explore SQLite databases used by browsers.

#### Installing WebBrowserPassView
1. Download WebBrowserPassView from the [NirSoft website](https://www.nirsoft.net/utils/web_browser_password.html).
2. Extract the downloaded zip file to a directory of your choice.

#### Installing BrowserHistoryViewer
1. Download BrowserHistoryViewer from the [Foxton Software website](https://www.foxtonsoftware.com/browser-history-viewer).
2. Run the installer and follow the on-screen instructions.

#### Installing SQLite Database Browser
1. Download SQLite Database Browser from the [official website](https://sqlitebrowser.org/dl/).
2. Run the installer and follow the on-screen instructions.

## Exercises

### Exercise 1: Extracting Browser History
**Objective**: Learn how to extract and view browser history from popular web browsers using BrowserHistoryViewer.

**Steps**:
1. Open BrowserHistoryViewer.
2. Select the web browsers you want to analyze (e.g., Chrome, Firefox, Edge).
3. Click on `Load History` to extract the browsing history.
4. Review the displayed history, including visited URLs, visit dates, and times.

**Expected Output**: You should be able to view the browsing history from the selected web browsers.

### Exercise 2: Recovering Stored Passwords
**Objective**: Use WebBrowserPassView to recover passwords stored in web browsers.

**Steps**:
1. Open WebBrowserPassView.
2. The tool will automatically detect and display stored passwords from various web browsers.
3. Review the list of recovered passwords, including the website, username, and password.

**Expected Output**: You should be able to recover and view stored passwords from various web browsers.

### Exercise 3: Analyzing Browser Cookies
**Objective**: Extract and analyze browser cookies to understand user activities and track potential malicious behavior.

**Steps**:
1. Locate the cookies database for the browser you want to analyze (e.g., `Cookies` file in the Chrome user data directory).
2. Open the cookies database using SQLite Database Browser.
3. Browse the `cookies` table to view the stored cookies, including the host, name, value, creation, and expiry dates.

**Expected Output**: You should be able to view and analyze browser cookies, identifying useful information about user activities.

### Exercise 4: Examining Browser Cache
**Objective**: Analyze the browser cache to uncover information about accessed web content and resources.

**Steps**:
1. Locate the cache storage directory for the browser you want to analyze (e.g., `Cache` folder in the Chrome user data directory).
2. Use BrowserHistoryViewer to load and view cache entries:
   - Select `File` > `Load Cache` and choose the cache folder.
   - Review the list of cached items, including URLs, cache types, and sizes.

**Expected Output**: You should be able to view and analyze browser cache entries, identifying accessed web content and resources.

### Exercise 5: Interpreting Download Records
**Objective**: Extract and interpret download records to track files downloaded by the user.

**Steps**:
1. Locate the downloads database for the browser you want to analyze (e.g., `History` file in the Chrome user data directory).
2. Open the downloads database using SQLite Database Browser.
3. Browse the `downloads` table to view the download records, including URLs, file paths, start and end times.

**Expected Output**: You should be able to view and interpret download records, identifying files downloaded by the user.

---

With these exercises, you will gain practical experience in extracting and interpreting browser artifacts on Windows. This will enhance your skills in digital forensics and help you effectively investigate user activities by uncovering valuable evidence stored by web browsers.
