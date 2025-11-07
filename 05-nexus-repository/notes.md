# 🧩 Nexus Repository Manager Setup and Integration  
**Topic:** Cloud & Artifact Management (IaaS – Nexus Repository)  
**Bootcamp:** TechWorld by Nana – DevOps Bootcamp  
**Author:** Onyekaozuru Tochukwu David  
**Date:** November 2025  

---

## 🎯 Overview
In this section of the DevOps Bootcamp, I learned how to **install, configure, and use Nexus Repository Manager** on a cloud server (DigitalOcean droplet).  
Nexus acts as a **central artifact repository** for managing build artifacts from tools like **Maven** and **Gradle**, which is an important step in a CI/CD pipeline.

---

## 🖥️ Server Setup

### 🔹 Step 1: Create Droplet on DigitalOcean
- Chose region: **London (LON1)** for best latency from Nigeria  
- OS: **Ubuntu 22.04 (Jammy)**  
- Droplet size: 2vCPU, 8GB RAM (recommended for Nexus)
- Added my **SSH key** during droplet creation for secure login  

```bash
ssh root@<your-droplet-ip>
```
## Install Java (Nexus Dependency)

### Nexus requires Java (OpenJDK 8+). Installed it using:
```bash
sudo apt update
sudo apt install openjdk-17-jdk -y
java -version
```
## 📦 Download & Install Nexus
```bash
cd /opt
sudo wget https://download.sonatype.com/nexus/3/latest-unix.tar.gz
sudo tar -xvzf latest-unix.tar.gz
sudo mv nexus-3* nexus
sudo adduser nexus
sudo chown -R nexus:nexus /opt/nexus /opt/sonatype-work
```
### Edit the Nexus configuration file to assign the service user:
```bash
sudo nano /opt/nexus/bin/nexus.rc
run_as_user="nexus"
```

## 🧠 Start Nexus as a Service
```bash
 /opt/nexus/bin/nexus start
```
### Access Nexus in your browser:
👉 ```http://<your-droplet-ip>:8081```

## 🔑 Login & Initial Setup
- Default admin credentials are found in:
  ```cat /opt/sonatype-work/nexus3/admin.password```
- created new repositories
- Created a new user: devops and added role

## 🧩 Integrating Gradle with Nexus
### build.gradle snippet:
```groovy
plugins {
    id 'java'
    id 'maven-publish'
}

group = 'com.example'
version = '1.0.0-SNAPSHOT'

publishing {
    publications {
        mavenJava(MavenPublication) {
            from components.java
        }
    }
    repositories {
        maven {
            def releasesRepoUrl = "http://<your-droplet-ip>:8081/repository/maven-releases/"
            def snapshotsRepoUrl = "http://<your-droplet-ip>:8081/repository/maven-snapshots/"
            url = version.endsWith('SNAPSHOT') ? snapshotsRepoUrl : releasesRepoUrl

            credentials {
                username = project.findProperty("nexusUsername") ?: "devops"
                password = project.findProperty("nexusPassword") ?: "your-password"
            }
            allowInsecureProtocol = true
        }
    }
}
```
### Publish your build:
``` ./gradlew clean build publish```

## 🧩 Integrating Maven with Nexus
### In your project’s pom.xml:
```xml
<distributionManagement>
  <snapshotRepository>
    <id>nexus-snapshots</id>
    <url>http://<your-droplet-ip>:8081/repository/maven-snapshots/</url>
  </snapshotRepository>
  <repository>
    <id>nexus-releases</id>
    <url>http://<your-droplet-ip>:8081/repository/maven-releases/</url>
  </repository>
</distributionManagement>
```
### Configure your ```~/.m2/settings.xml```:
```xml
<servers>
  <server>
    <id>nexus-snapshots</id>
    <username>devops</username>
    <password>your-password</password>
  </server>
  <server>
    <id>nexus-releases</id>
    <username>devops</username>
    <password>your-password</password>
  </server>
</servers>
```
### Deploy your artifact:
```mvn clean deploy```

## 🧠 Key Takeaways

- Nexus centralizes and manages build artifacts
- Integrated successfully with both Gradle and Maven
- Understood the difference between Snapshots and Releases
- Practiced user management, repository setup, and authentication
- Learned to publish builds directly to a private Nexus repository

