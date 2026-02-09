# Azure Project: Web Server Deployment on Windows Virtual Machine

This repository documents the deployment of a **Windows Server Virtual Machine on Microsoft Azure**, the configuration of **network security rules**, and the installation of **Internet Information Services (IIS)** to host a publicly accessible website.

---

## 📌 Project Overview

The goal of this project was to provision a Windows-based VM in Azure, configure secure inbound connectivity, deploy a web server role, and validate public access via HTTP.

---

## 🖥️ Virtual Machine Configuration

| Setting               | Value                                      |
| --------------------- | ------------------------------------------ |
| **VM Name**           | `VirtualMachine1`                          |
| **Operating System**  | Windows Server 2025 Datacenter (x64, Gen2) |
| **Region**            | Italy North (Zone 3)                       |
| **VM Size**           | Standard E2s v3 (2 vCPUs, 16 GiB RAM)      |
| **Public IP Address** | `4.232.138.252`                            |
| **Resource Group**    | `vm`                                       |

---

## 🌐 Networking & Security Rules

The following **Inbound Port Rules** were configured to allow secure access:

* **RDP (Port 3389)** – Enabled for remote administration
* **HTTP (Port 80)** – Enabled to allow public web access

These rules were applied using Azure Network Security Groups (NSG).

---

## 🔐 Remote Desktop Connection (RDP)

Steps used to connect to the virtual machine:

1. Navigated to **Virtual Machine → Connect** in the Azure Portal
2. Selected **Native RDP**
3. Downloaded the RDP file for the public IP: `4.232.138.252`
4. Logged in using the administrator account:

   * **Username:** `azureuser`

---

## 🌍 IIS Web Server Installation

After connecting to the VM, the **IIS role** was installed using PowerShell.

### PowerShell Command

```powershell
Install-WindowsFeature -Name Web-Server -IncludeManagementTools
```

### Installation Result

* **Success Status:** `True`
* **Exit Code:** `Success` (or `NoChangeNeeded` if already installed)
* **Restart Required:** No

---

## ✅ Deployment Verification

The installation was verified by accessing the public IP address from a local browser:

```
http://4.232.138.252
```

The default **Internet Information Services (IIS) Welcome Page** was displayed successfully, confirming that the web server was operational and publicly accessible.

---

## 🧹 Resource Cleanup (Cost Management)

To avoid unnecessary charges on the **Azure for Students** subscription, all resources were removed after completing the lab.

### Cleanup Steps

1. Open the **Azure Portal**
2. Navigate to **Resource Groups**
3. Locate the resource group named **`vm`**
4. Select **Delete resource group**
5. Confirm deletion by typing the resource group name

This action removes:

* Virtual Machine
* OS Disk
* Network Interface
* Public IP Address

---

## 📅 Project Information

* **Project Date:** February 9, 2026
* **Platform:** Microsoft Azure
* **Administrator Account:** `azureuser`

---

## 🚀 Notes

This project demonstrates foundational skills in:

* Azure Virtual Machines
* Windows Server administration
* IIS web server deployment
* Network security configuration

Ideal for **cloud fundamentals labs**, **portfolio projects**, or **IT/Cloud learning paths**.
