# Jenkins Installation on Ubuntu

## OS Support
- Ubuntu 22.04 LTS (recommended)
- Ubuntu 24.04 LTS

## Java Requirement
- Java 17 (LTS – recommended)
- Java 21 (LTS – latest)

> Jenkins requires Java. Java 11 is deprecated and should not be used.

---

## Step 1: Update system
```bash
sudo apt update && sudo apt upgrade -y

## Step 2: Install Java

sudo apt install fontconfig openjdk-21-jre

## To check java version

java -version

## Step 3: Add Jenkins repository key

sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key

## Step 4: Add Jenkins repository

echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null

## Step 5: Install Jenkins

sudo apt update
sudo apt install jenkins -y

## Step 6: Start and enable Jenkins

sudo systemctl start jenkins
sudo systemctl enable jenkins

## Check Jenkins status:

systemctl status jenkins
#or
service jenkins status

## Step 7: Access Jenkins UI
## Open your browser and go to:

http://localhost:8080

## Get initial admin password:

sudo cat /var/lib/jenkins/secrets/initialAdminPassword


