
![Leonardo_Phoenix_10_A_professional_and_modern_illustration_sho_1(2)(1)](https://github.com/user-attachments/assets/14fcd932-7ed4-478f-b308-fc93787533be)


How to Install Kasm Workspaces on Proxmox: A Step-by-Step Guide

Kasm Workspaces is a powerful solution for delivering containerized, browser-based desktops and applications. In this guide, we’ll cover how to install Kasm Workspaces on Proxmox in a few simple steps.

Prerequisites

Proxmox VE Installed: Ensure you have Proxmox installed and configured.

Adequate Resources: At least 4 CPU cores, 8GB of RAM, and 50GB of storage for the Kasm VM/CT.

Internet Access: Required for downloading Kasm Workspaces.

Step 1: Prepare a Virtual Machine (VM)

Log into Proxmox:

Access the Proxmox web interface.

Create a New VM:

Go to Datacenter > Create VM.

Assign a name (e.g., kasm-workspaces).

Choose an ISO image for Ubuntu 20.04+ or Debian 11 (recommended by Kasm).

Allocate Resources:

CPU: Assign 4 cores.

Memory: Assign 8GB (8192MB).

Disk: Set at least 50GB.

Network Configuration:

Attach a network interface using the default bridge.

Finish and Start the VM:

Complete the wizard and boot the VM.

Step 2: Install the Operating System

Access the VM Console:

Open the console from the Proxmox web interface.

Install Ubuntu/Debian:

Follow the installer steps and configure a static IP for easier access later.

Update the System:

    sudo apt update && sudo apt upgrade -y

Step 3: Download and Install Kasm Workspaces

Download the Installer:

    curl -O https://kasm-static-content.s3.amazonaws.com/kasm_release_1.13.0.2.tar.gz

(Check the Kasm website for the latest release URL.)

Extract the Installer:

    tar -xvzf kasm_release_1.13.0.2.tar.gz

Run the Installer:

    cd kasm_release
    sudo ./install.sh

Follow the Prompts:

The script will install Docker and configure Kasm automatically.

Step 4: Access Kasm Workspaces

Retrieve Access URL:

After installation, note the provided URL (e.g., https://your-server-ip).

Login:

Default credentials:

Username: admin

Password: kasm2023

Change the password after logging in for security.

Step 5: Post-Installation Configuration

Enable SSL:

Replace the self-signed certificate with a valid SSL certificate for production use.

Create User Accounts:

Add users or integrate with LDAP/SSO if needed.

Optimize Resources:

Adjust container resources in the Kasm admin panel to match your Proxmox environment.

Conclusion

You now have Kasm Workspaces running on Proxmox, ready to deliver containerized desktops and apps. This setup is perfect for secure, scalable remote access in both personal and enterprise environments.

