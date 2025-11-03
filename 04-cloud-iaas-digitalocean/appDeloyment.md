## 🌩️ Cloud & Infrastructure as a Service (IaaS) — DigitalOcean Deployment

### 🚀 Overview  
In this module of my **TechWorld by Nana DevOps Bootcamp**, I learned about **Cloud & Infrastructure as a Service (IaaS)** and how to deploy applications on cloud servers.  
I used **DigitalOcean Droplets** to host and deploy a sample **Java + React application** that I built locally using **Gradle** inside **IntelliJ IDEA**.

---

### 🧠 What I Accomplished

#### 1. Created a Droplet on DigitalOcean
- Region: **London (LON1)** – best performance from Nigeria  
- Image: **Ubuntu 22.04 (Jammy Jellyfish)**  
- Authentication: **SSH key** (no password login)  

---

#### 2. Built the Java Application Locally
- Opened my Spring Boot project in IntelliJ and ran the Gradle build command:
  ```bash
  ./gradlew build
- The output ```.jar``` file was generated inside ``` build/libs/```

#### 3. Transferred the JAR to the Droplet
- Used SCP (Secure Copy) to move the file to the server:
  ```bash
  scp build/libs/app.jar root@<droplet_ip>:/home/root/
#### 4. Deployed the Application on the Droplet
Connected via SSH:
```bash
ssh root@<droplet_ip>
```
#### 5. Ran the application:
```java -jar app.jar```
- The app started successfully and was accessible via the droplet’s public IP.
Configured Linux User & Permissions

#### 6. Created a new user:
```adduser devopsuser```


#### 7. Added user to the sudo group:
```usermod -aG sudo devopsuser```

#### 8. Verified privileges by switching user:
```bash
su - devopsuser
sudo apt update
```

### 🧩 Tools & Concepts Covered

☁️ DigitalOcean Droplets
🧰 Gradle Build Tool
💻 SSH & SCP
🧑‍💻 Linux User Management
🚀 Java Application Deployment

### 🧠 Key Takeaways

Understood how cloud VMs (Droplets) serve as deployable infrastructure.
Learned to securely connect and transfer files using SSH & SCP.
Practiced managing users and permissions on a Linux server.
Experienced the full flow from local build → cloud deployment.
