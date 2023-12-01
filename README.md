/++# Azure Sentinel RDP Honeypot

## Overview

Welcome to the Azure Sentinel RDP Honeypot project! This repository showcases a dynamic setup using Azure Sentinel, where a Windows VM honeypot is created, the firewall is disabled, attackers are lured, RDP logs are gathered via PowerShell, and attacks are visualized worldwide using Azure Sentinel.

## Description

The PowerShell script in this repository plays a pivotal role in parsing Windows Event Log information for failed RDP attacks. It also utilizes a third-party API (ipgeolocation.io) to collect geographic information about the attackers' locations.

In the accompanying demo:

1. **VM Creation and Configuration:**
   - A Windows VM is created and configured, accessible through Remote Desktop Protocol (RDP).
   - Security events for RDP failed connections are monitored within the Windows Event Viewer.

2. **PowerShell Script for Log Enrichment:**
   - A PowerShell script is developed to extract and log RDP failed connection events.
   - The script enriches the logs with geolocation data using the ipgeolocation.io API.

3. **Log Analytics Integration:**
   - The VM is connected to Log Analytics, utilizing Kusto Query Language (KQL) to abstract raw data from RDP failed logs.

4. **Azure Sentinel Workbook:**
   - The enriched data is sent to Microsoft Sentinel's workbook, providing a visual representation of RDP failed attempts worldwide.
   - The workbook includes graphs illustrating the frequency and geographical distribution of RDP failed attempts.

### Features

- **RDP Event Fail Logs to IP Geographic Information:** Extracts RDP failed logon logs from the Windows Event Viewer and retrieves geolocation information using the ipgeolocation.io API.

- **Live Attack Visualization:** Azure Sentinel is configured to connect to a live virtual machine honeypot, capturing real-time RDP brute force attacks.

- **Custom PowerShell Script:** A custom PowerShell script is used to enrich logs with geolocation data, providing a comprehensive view of attackers' locations.

- **Log Analytics Integration:** Connects the VM to Log Analytics, using KQL to abstract raw data from RDP failed logs.

- **Azure Sentinel Workbook:** Visualizes enriched data in Microsoft Sentinel's workbook, graphing the frequency and geographical distribution of RDP failed attempts.

## Languages Used

- **PowerShell:** Extracts RDP failed logon logs from the Windows Event Viewer.

## Utilities Used

- **ipgeolocation.io:** IP Address to Geolocation API for obtaining geographic information about attackers.

## Image Analysis Dataflow

Explore the world map of incoming attacks after 24 hours, revealing custom logs enriched with geodata for a comprehensive analysis.

![World Map of Incoming Attacks](images/world_map_attacks.png)
