# Java Maven Hello World with Jenkins

This project demonstrates how to set up a simple Java Maven build job in Jenkins — your first step into Continuous Integration (CI)!

## Objective

Use Jenkins to build a basic Java application using Maven and verify successful build output.

## Tools Required

- **Jenkins** (Locally installed or via Docker)
- **Java JDK 8 or 11**
- **Maven**
- **Git** (optional)

## Code

### HelloWorld.java

public class HelloWorld 
{
    public static void main(String[] args) 
    
    {
            System.out.println("Hello, Jenkins + Maven!");
            }    

# Steps to Run Jenkins Job

**1. Start Jenkins**

>>docker run -p 8080:8080 jenkins/jenkins:lts

Access Jenkins at: http://localhost:8080

**2. Configure Maven in Jenkins**

- Go to Manage Jenkins → Global Tool Configuration
- Under Maven, click Add Maven
- Name: Maven_3.8.6 (or your version)
- Check “Install automatically” or set path if installed locally

**3. Create Jenkins Freestyle Project**

- Go to New Item → Freestyle Project → Name it hello-java-maven
- In Source Code Management, leave as "None" (or use Git if repo is available)
- In Build, click Add build step → Invoke top-level Maven targets
- Goals: clean package
- Save and click Build Now

**✅ Expected Output**

In Console Output, you should see: [INFO] BUILD SUCCESS

**Notes**
- Make sure Java and Maven are installed and configured.
- If using Git, push this project to a GitHub repo and use SCM in Jenkins.
