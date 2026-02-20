# Jenkins Installation on Fedora

## OS Support
- Fedora 39+
- Red Hat Enterprise linux (REHL)
- Rocky Linux

## Java Requirement
- Java 17 (LTS – recommended)
- Java 21 (LTS – latest)

> Jenkins requires Java. Java 11 is deprecated and should not be used.

---

## Step 1: Update system
```bash
sudo dnf update -y
```
## Step 2: Add Jenkins repository
```bash
sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/rpm-stable/jenkins.repo
```

## Step 3: Upgrading system 
```bash
sudo dnf upgrade
```
## Step 4: Install Java
```bash
sudo dnf install fontconfig java-21-openjdk
```
## Step 5: Install Jenkins
```bash
sudo dnf install jenkins -y
```
## Step 6: Daemon reload
```bash
sudo systemctl daemon-reload
```
## Step 7: Start and enable Jenkins
```bash
sudo systemctl enable --now jenkins
```
## Check Jenkins status:
```bash
systemctl status jenkins
```
## Step 8: Allow jenkins port on firewall🔥
```bash 
sudo firewall-cmd --permanent --add-port=8080/tcp
sudo firewall-cmd --reload
```

## Step 9: Access Jenkins UI

### On Local VM:
```bash 
http://localhost:8080
```

### On Cloud VM / Remote server:
```bash
http://<VM-IP>:8080
```

## Step 10: Get initial admin password:
```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

