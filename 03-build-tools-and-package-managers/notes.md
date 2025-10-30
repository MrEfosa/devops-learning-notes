# 🧠 DevOps Learning Journal — Build Tools & Package Managers

**📅 Date:** October 28, 2025  
**👨‍💻 Topic:** Build Tools, Package Managers & IDE Setup  

---

## 🔹 Progress Summary

Today, I focused on understanding and setting up **build tools** and **package managers** for Java and Node.js applications.  
I also learned how to use **IntelliJ IDEA** for managing Java projects using both **Maven** and **Gradle**.  
This was an important step in learning how applications are built, managed, and automated in a DevOps environment.

---

## 🔹 Tools Installed

| Tool | Purpose | Status |
|------|----------|---------|
| **IntelliJ IDEA** | Integrated Development Environment (IDE) for Java | ✅ Installed |
| **JDK 17** | Java Development Kit for building and running Java apps | ✅ Installed |
| **Maven** | Java build automation and dependency management tool | ✅ Installed |
| **Gradle** | Java build automation tool (alternative to Maven) | ✅ Installed |
| **Node.js** | JavaScript runtime for building web applications | ✅ Installed |
| **npm** | Node.js package manager for managing dependencies | ✅ Installed |
| **Git** | Version control system | ✅ Installed & Configured |

---

## 🔹 Tasks Completed

### 🧩 1. Cloned a Java Maven Project
```bash
git clone https://github.com/username/sample-maven-app.git
cd sample-maven-app
mvn clean install
```
### 🧩 2. Cloned a Java Gradle Project
```bash
git clone https://github.com/username/sample-gradle-app.git
cd sample-gradle-app
gradle build
```
### 🧩 3. Set Up a Node.js Application
```bash
git clone https://github.com/username/sample-node-app.git
cd sample-node-app
npm install
npm start
```
## 🔹 Useful Commands
| Command             | Description                                    |
| ------------------- | ---------------------------------------------- |
| `mvn clean install` | Clean and build a Maven project                |
| `gradle build`      | Build a Gradle project                         |
| `gradle clean`      | Remove old build files                         |
| `npm install`       | Install Node.js dependencies                   |
| `npm start`         | Start a Node.js application                    |
| `git pull`          | Fetch and merge changes from remote repository |
| `git push`          | Push local commits to remote repository        |


## 🧠 Lessons Learned
- Build Tools like Maven and Gradle automate compiling, testing, and packaging applications.

- Package Managers like npm handle dependency installation and updates.

- IntelliJ makes managing Java projects easier by integrating with Maven and Gradle.

- Understanding build automation is critical for continuous integration (CI/CD) workflows.

- Git is essential for version control and collaboration in all DevOps projects.

## 🚀 Summary
Today, I completed setup for key development tools used in DevOps — IntelliJ, Maven, Gradle, and Node.js — and practiced cloning, building, and running sample projects.
This forms a strong foundation for upcoming topics like Jenkins, CI/CD pipelines, and containerization.
