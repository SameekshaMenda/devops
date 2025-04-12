#  Jenkins Pipelines for Beginners

This guide is for **beginners** who want to understand and create **pipelines in Jenkins**. Pipelines help you automate the process of building, testing, and deploying applications.

---

##  What is a Jenkins Pipeline?

A **Pipeline** is a set of steps (scripted) that Jenkins runs to automate software delivery. It's written using **Groovy-based syntax** and stored in a file called `Jenkinsfile`.

---

##  Types of Pipelines

| Type         | Description                         |
|--------------|-------------------------------------|
| **Declarative** | Easy-to-read, structured syntax (recommended for beginners) |
| **Scripted**    | More flexible, written in Groovy (advanced users) |

# Creating a Pipeline in Jenkins
----------------------------------
- Go to Jenkins Dashboard

- Click "New Item"

- Enter a name (e.g., MyPipeline)

- Select "Pipeline" and click OK

- In the Pipeline section, choose:

- Definition: Pipeline script (for now; later, use "Pipeline script from SCM" to pull Jenkinsfile from GitHub)

- Script: Paste the pipeline code above

- Click Save

- Click Build Now

- Check the Blue bar or go to Console Output to view results

basic setup:
============
- Manage jenkins ->Plugins->available plugins
- maven
- deploy to container->install

http://18.209.63.62:8080/

configuration in program file:

![image](https://github.com/user-attachments/assets/acc5e2cb-7243-40e4-af2c-0dd840420a2e)

H/3 17 27 3 5

![image](https://github.com/user-attachments/assets/d49fa543-93f5-4c8e-b876-b0104b1c1338)

![image](https://github.com/user-attachments/assets/97b02c95-125f-4f7e-8cf0-c1b8ef617c52)

![image](https://github.com/user-attachments/assets/a7a72b40-c7ff-4d1e-84fd-87aaa4a36a19)


