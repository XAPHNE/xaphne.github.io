---
layout: post
title: How to setup IntelliJ IDEA IDE and JDK on Ubuntu
date: 2023-09-05 15:36:00 +0530
image: /assets/images/blog/laptop-coding-371x270.png
author: XAPHNE
tags: IntelliJ, JDK, Ubuntu, Linux, Debian, Environment Variables 
---
**Setting up IntelliJ IDEA IDE and JDK on Ubuntu or other Debian based distributions**

##### Introduction:

IntelliJ IDEA is a popular integrated development environment (IDE) for Java development. It offers a wide range of features to streamline the development process and enhance productivity. To get started with IntelliJ IDEA, you'll first need to install the IDE and set up the Java Development Kit (JDK). In this blog post, we'll walk you through the process of installing IntelliJ IDEA, downloading the JDK from within IntelliJ IDEA, and setting up Java environment variables on an Ubuntu system.

&nbsp;

### Step 1: Install IntelliJ IDEA

1. **Download IntelliJ IDEA:** Go to the [JetBrains website](https://www.jetbrains.com/idea/download/) and download the Community or Ultimate edition of IntelliJ IDEA, depending on your requirements. You can also use the Flatpak package manager to install IntelliJ IDEA if you prefer.

2. **Install IntelliJ IDEA via Flatpak (recomended):** If you choose to use Flatpak, open your terminal and run the following command:

   ```bash
   sudo flatpak install flathub com.jetbrains.IntelliJ-IDEA-Community
   ```

   This command will install the Community edition. Replace `IntelliJ-IDEA-Community` with `IntelliJ-IDEA-Ultimate` if you want to install the Ultimate edition.

3. **Launch IntelliJ IDEA:** Once the installation is complete, you can launch IntelliJ IDEA from the Applications menu or by running `flatpak run com.jetbrains.IntelliJ-IDEA-Community` in the terminal.

### Step 2: Download and Configure JDK

1. **Open IntelliJ IDEA:** Launch IntelliJ IDEA.

2. **Create a New Project:** Click on "Create New Project" or open an existing project if you have one.

3. **Configure Project SDK:** If you haven't configured a JDK yet, you'll see a message saying "Project SDK is not defined." Click on the "New Project" button next to it.

4. **Add JDK:** In the "Project SDK" dialog, select "Download JDK..." to download a JDK directly from JetBrains. You can also choose "Add JDK..." to configure an existing JDK if you have one installed on your system.

5. **Select JDK Version:** Choose the version of the JDK you want to download or configure. IntelliJ IDEA will automatically download and set up the selected JDK for your project.

6. **Configure Project Language Level:** Set the language level for your project. This determines which language features are available to you. Usually, it's best to select the latest available version.

### Step 3: Set up Java Environment Variables on Ubuntu

1. **Set JAVA_HOME and PATH:** To set the `JAVA_HOME` and `PATH` environment variables, open the terminal and run:

   ```bash
   echo '# Setting JAVA_HOME and PATH variables for installed JDK' >> ~/.bashrc
   echo 'export JAVA_HOME="~/.jdks/corretto-17.0.8.1/"' >> ~/.bashrc
   echo 'export PATH="$JAVA_HOME/bin:$PATH"' >> ~/.bashrc
   source ~/.bashrc
   ```
   **Note:** Make sure to change the path according to your jdk directory

   This sets the `JAVA_HOME` and `PATH` variables to the path of the default JDK installation.

2. **Verify Installation:** To verify that Java is correctly installed and the environment variable is set, run the following commands:

   ```bash
   java --version
   javac --version
   echo $JAVA_HOME
   echo $PATH
   ```

   You should see information about the installed Java and Java Compiler version and the `JAVA_HOME` and `PATH` variable's path.

### Conclusion:

Setting up IntelliJ IDEA and the JDK on Ubuntu is a straightforward process. With these steps, you'll have a fully functional Java development environment ready to build your projects. IntelliJ IDEA's user-friendly interface and powerful features will help streamline your development workflow, making it easier to create Java applications. Happy coding!