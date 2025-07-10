# SonarQube + Jenkins Integration

This project connects **SonarQube** with **Jenkins** to check code quality automatically every time someone pushes code or creates a pull request.

SonarQube checks the code for bugs, security issues, code smells, and test coverage. Jenkins runs these checks as part of the CI/CD pipeline, so we find problems early — before the code goes live.

We also added **quality gates**, which means if the code doesn't meet certain quality rules, the build will fail. This helps the team keep the code clean, safe, and easy to maintain.

This setup is useful for any project where you want to catch issues early, write better code, and keep your development process smooth and reliable.


## 📸 Jenkins Dashboard

![SonarQube Dashboard](./assets/sqube-success.png)

## 📸 SonarQube Dashboard

![SonarQube Dashboard](./assets/jenkins-success.png)
