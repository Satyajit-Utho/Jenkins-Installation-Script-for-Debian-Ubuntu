# Jenkins-Installation-Script-for-Debian-Ubuntu
Jenkins

This repository provides a simple Bash script to install Jenkins on a Debian-based Linux system (e.g., Ubuntu). It handles all required dependencies and repository setup for a smooth Jenkins installation.

🧰 What It Does
The script:

Updates the system package index
Installs required dependencies, including Java 17
Adds Jenkins’ official GPG key
Adds Jenkins’ stable Debian repository

🖥️ Requirements
Debian/Ubuntu-based Linux server
Root or sudo privileges
Internet connectivity

📄 Script
#!/bin/bash

Update the system package index
apt update

Install necessary dependencies
apt install -y wget gnupg fontconfig openjdk-17-jre

Verify Java installation
java -version

Add Jenkins repository key
wget -O /usr/share/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key

Add Jenkins repository to sources list
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/" | tee /etc/apt/sources.list.d/jenkins.list > /dev/null

📜 License
This script is open-source and available under the MIT License.
