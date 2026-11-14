# DevOps CI/CD Pipeline — Jenkins, Python & Maven

A hands-on DevOps project demonstrating automated build and execution workflows using **Jenkins, Python, Java and Apache Maven**.

This project uses a Jenkins Declarative Pipeline to execute a Python program, verify Maven installation, build a Java application and execute the generated JAR file.

## Overview

The repository demonstrates how multiple development tools can work together through a single automated Jenkins pipeline.

### Key Features

- Automated CI pipeline using Jenkins.
- Python program execution through Jenkins.
- Java application development using Java 17.
- Maven-based compilation and packaging.
- Executable JAR generation.
- Automated JAR execution.
- Pipeline success and failure handling.

## Technology Stack

| Technology | Purpose |
|---|---|
| Jenkins | CI/CD automation |
| Python | Python program execution |
| Java 17 | Java application development |
| Apache Maven | Build and dependency management |
| Windows Batch | Executing commands on the Jenkins agent |

## Project Structure

```text
DevOps/
│
├── HelloWorld.py
│
├── Jenkinsfile
│
└── Maven Java/
    │
    ├── pom.xml
    │
    ├── src/
    │   └── main/
    │       └── java/
    │           └── HelloWorld.java
    │
    └── target/
        └── maven-hello-world-1.0.jar
```

*Note: The `target/` directory contains Maven-generated build output.*

## Jenkins Pipeline Workflow

The Jenkinsfile implements four sequential stages:

### 1. Python Build

- Checks the Python installation.
- Displays the installed Python version.
- Executes `HelloWorld.py`.

### 2. Maven Version

- Checks the Apache Maven installation.
- Displays the installed Maven version.

### 3. Maven Build

- Executes Maven's clean and package goals.
- Compiles the Java source code.
- Packages the application into an executable JAR.

Command:

```bash
mvn -f "Maven Java/pom.xml" clean package
```

### 4. Run JAR

- Executes the generated Java application.
- Uses the configured Java runtime.
- Runs `maven-hello-world-1.0.jar`.

The pipeline also includes post-build actions to report successful execution or pipeline failure.

## Prerequisites

Before running this project, ensure the Jenkins agent has:

- Jenkins with Pipeline support.
- Python installed.
- JDK installed.
- Apache Maven installed.
- Access to the GitHub repository.

**Important:** The current Jenkinsfile uses Windows-specific absolute paths for Python, Java and Maven. These paths must match the machine running Jenkins.

The current configuration points `JAVA_HOME` to JDK 21, while the Maven project targets Java 17.

## Run Locally

### 1. Clone the Repository

```bash
git clone https://github.com/Rashmi-Negi/DevOps.git
```

```bash
cd DevOps
```

### 2. Run the Python Program

```bash
python HelloWorld.py
```

### 3. Build the Java Maven Project

```bash
mvn -f "Maven Java/pom.xml" clean package
```

### 4. Execute the Generated JAR

```bash
java -jar "Maven Java/target/maven-hello-world-1.0.jar"
```

## Run Using Jenkins

1. Open your Jenkins dashboard.
2. Create a new **Pipeline** job.
3. Configure the GitHub repository URL.
4. Select the `main` branch.
5. Configure Jenkins to use the repository's `Jenkinsfile`.
6. Save the pipeline configuration.
7. Click **Build Now**.
8. Open **Console Output** to monitor the execution.

Jenkins will automatically execute all four stages in sequence.

## Learning Outcomes

Through this project, you can understand:

- Fundamentals of DevOps and CI/CD.
- Jenkins Declarative Pipeline syntax.
- Automating development workflows.
- Integrating Python and Java into Jenkins.
- Maven project structure and lifecycle.
- Java compilation and JAR packaging.
- Running build artifacts through CI pipelines.
- Monitoring pipeline execution through Jenkins console logs.

## Project Scope

This is an introductory CI/CD implementation focused on build automation and application execution.

The current implementation does not include automated testing, Docker containerization, artifact publishing or production deployment.

## Repository

**GitHub:** [Rashmi-Negi/DevOps](https://github.com/Rashmi-Negi/DevOps)

---

<p align="center">
  <b>Learning DevOps Through Practical Implementation</b><br>
  <sub>Jenkins • Python • Java • Maven</sub>
</p>
