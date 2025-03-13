# Home SOC in Microsoft Azure: A Practical Guide

This repository demonstrates how to set up a **Home SOC (Security Operations Center) in Microsoft Azure**. We’ll deploy and configure a virtual machine as a honeypot, gather logs in a central repository, and integrate Microsoft Sentinel to capture and analyze real-world attack data.

---

### Lab Overview
This project showcases how to build a simple security monitoring environment in Azure. By creating a low-interaction honeypot (i.e., a publicly exposed virtual machine), we can collect attack attempts and analyze them in Azure’s SIEM solution, Microsoft Sentinel. Key objectives include:

Deploying a Windows VM as a honeypot.
Configuring traffic rules to allow inbound connections for logging.
Setting up centralized logging with Azure Log Analytics.
Visualizing attacks in Sentinel via custom queries and an interactive map.
Note: Leaving a virtual machine running 24/7 in Azure may incur costs. Consider stopping or deallocating the VM when not in use

---

### Key Concepts Covered
- **Honeypot Development**:
  - Creating a publicly accessible Windows VM to attract real-world malicious traffic.
- **Log Forwarding & Analysis**:
  - Sending security events to Azure Log Analytics Workspace and Microsoft Sentinel.
- **Kusto Query Language (KQL)**:
  - Using KQL queries to investigate and filter security events in Azure.
- **Geolocation Enrichment**:
  - Incorporating IP-to-Geo watchlists for deeper insights into attack origins.
- **Attack Vizualization**:
  - Building a Sentinel Workbook to display attacks on an interactive map.
- **Hands-On Steps**:
  - Setting up a virtual machine (VM) as a HoneyPot.
  - Exposing the Honeypot.
  - Set up Log Analytics Workspace (LAW).
  - Enable Microsoft Sentinel.
  - Add GeoIP Data.
  - Build a visual Attack Map Workbook.

- **Tools Used**:
  - Azure Subscription (preferably free tier, if available)
  - Windows 10/11 Virtual Machine image in Azure (or compatible OS)
  - Log Analytics Workspace & Microsoft Sentinel (for SIEM functionality)

---

### Lab Workflow

**Environment Setup**:
   - Configure a VM in Azure.
   - Prepare the VM as a honeypot.
  

**Allow Inbound Traffic**
   - Access the Network Security Group (NSG) linked to your VM.
   - Create or modify an inbound security rule to allow the necessary (for a honeypot, you might open broader inbound access, but be aware of security risks).
     
     
**Disable the Windows Firewall**
   - RDP into your VM using its public IP address, username, and password.
  

**Central Log Repository & KQL**:
   - Create a Log Analytics Workspace (LAW)
   - Add Microsoft Sentinel to your LAW
   - Create a Data Collection Rule specifying which events to collect.
   - Your VM's SecurityEvent logs will now flow to the Log Analytics Workspace.

   

**Run a Basic KQL Query**:
   
  


**Log Enrichment with GeoIP Data**:
   - Prepare a GeoIP CSV
   - Create a Watchlist in Sentinel
   - After the watchlist import completes, run the following query:
     
**Attack Map Creation**:
   - Create a New Workbook in Sentinel
   - Add the Attack Map (JSON) using Advanced Editor
   - Review the Real-Time Attack Map

---

### Why This Lab?
By following the steps above, you’ll gain practical experience in:
- Configuring a Honeypot and exposing it to real-world threats.
- Collecting and Analyzing Logs via Azure Log Analytics and Microsoft Sentinel.
- Enriching Security Data with IP geolocation to track attack sources.
- Visualizing Attack Traffic in a clear, interactive workbook.
- These skills are highly relevant for anyone interested in SOC operations, cloud security, or general cybersecurity analytics.

---
