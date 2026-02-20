# Jenkins Installation on Fedora

## OS Support
- Fedora 39+
- Rwd Hat Enterprise linux (REHL)
- Rocky Linux

## Java Requirement
- Java 17 (LTS – recommended)
- Java 21 (LTS – latest)

> Jenkins requires Java. Java 11 is deprecated and should not be used.

---

## Step 1: Update system
```bash
sudo dnf update -y
sudo reboot
```
## Step 2: Install Java
```bash
sudo dnf install java-21-openjdk -y
```
## To check java version
```bash
java -version
```
## Step 3: Add Jenkins repository key
```bash
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
```
## Step 4: Add Jenkins repository
```bash
sudo curl -o /etc/yum.repos.d/jenkins.repo \
https://pkg.jenkins.io/redhat-stable/jenkins.repo
```
## Step 5: Install Jenkins
```bash
sudo dnf install jenkins -y
```
## Step 6: Start and enable Jenkins
```bash
sudo systemctl start jenkins
sudo systemctl enable jenkins
```
## Check Jenkins status:
```bash
systemctl status jenkins
```

## Step 7: Access Jenkins UI
### Open your browser and go to:

### On Local machince
<p>http://localhost:8080</p>

### On Cloud VM / Remote server:
<p>http://server-public-ip:8080</p>

## Get initial admin password:
```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

