---
layout: post
title: Getting Started with XAMPP on Ubuntu - A Step-by-Step Guide for Beginners
date: 2023-09-06 12:46:00 +0530
image: /assets/images/blog/XAMPP-Installation-on-ubuntu-371x270.png
author: XAPHNE
tags: XAMPP, MySQL, Ubuntu, Linux, Debian, Desktop Shortcut 
---

**A Beginner's Guide to Installing XAMPP on Ubuntu or Debian-Based Distros**

As a budding web developer, having a local server environment is crucial for testing and developing web applications. XAMPP is a fantastic tool that streamlines this process, making it easier to work with PHP, MySQL, and Apache. In this beginner-friendly guide, we'll take you through the process of installing XAMPP on Ubuntu or other Debian-based Linux distributions. We'll also create a desktop shortcut for the XAMPP Control Panel and grant your user the necessary permissions to execute it without a password prompt.

&nbsp;

### Installing XAMPP

**Step 1: Download XAMPP**

To get started, you'll need to download XAMPP. Visit the official [XAMPP download page](https://www.apachefriends.org/index.html) and choose the appropriate Linux version (32-bit or 64-bit) for your system.

**Step 2: Install XAMPP**

1. Open your terminal, and navigate to the directory where you downloaded XAMPP. Use the following commands to make the installer executable and run it:

   ```bash
   chmod +x xampp-linux-x64-installer.run  # Replace with the actual filename you downloaded
   sudo ./xampp-linux-x64-installer.run
   ```

   Follow the on-screen instructions to complete the installation. By default, XAMPP will be installed in `/opt/lampp/`.

**Step 3: Create a Desktop Shortcut**

Now that XAMPP is installed, let's make it easier to access. We'll create a desktop shortcut for the XAMPP Control Panel.

1. Open your terminal, and create a `XAMPP.desktop` file using your preferred text editor:

   ```bash
   nano ~/.local/share/applications/XAMPP.desktop
   ```

2. Copy and paste the following code into the `XAMPP.desktop` file:

   ```bash
   [Desktop Entry]
   Version=1.0
   Encoding=UTF-8
   Name=XAMPP Control Panel
   Comment=Start and Stop XAMPP
   Exec=sudo /opt/lampp/manager-linux-x64.run
   Icon=/opt/lampp/htdocs/favicon.ico
   Categories=Application
   Type=Application
   Terminal=false
   ```

   Save the file and exit the text editor.

**Step 4: Grant Sudo Permission**

To execute the XAMPP Control Panel without a password prompt, we'll add a sudoers entry. Replace `your_system_user_name` with your actual username.

1. Open the sudoers file for editing:

   ```bash
   sudo visudo
   ```

2. Add the following line to the sudoers file:

   ```text
   your_system_user_name ALL=(root) NOPASSWD: /opt/lampp/manager-linux-x64.run
   ```

   Save and exit the editor.

That's it! You've successfully installed XAMPP, created a desktop shortcut for the Control Panel, and granted the necessary sudo permissions. Now, you can seamlessly develop and test your web applications on your local server environment. Happy coding!