# Qwitter-DevOps
![qwitter_devops](https://github.com/Qwitter/Qwitter-DevOps/assets/96792115/8995f2ce-5d6d-428c-8e0c-762ae5628e21)

This repository contains all the DevOps files needed for Qwitter (X clone). I have used various tools on this project, and it was deployed on Azure, and the database was hosted on AWS (RDS).

# Tools
- [Docker](https://github.com/Qwitter/Qwitter-DevOps#docker)
- [Jenkins](https://github.com/Qwitter/Qwitter-DevOps?tab=readme-ov-file#jenkins)
- [Prometheus](https://github.com/Qwitter/Qwitter-DevOps?tab=readme-ov-file#prometheus)
- [Grafana](https://github.com/Qwitter/Qwitter-DevOps?tab=readme-ov-file#grafana)
- [AWS](https://github.com/Qwitter/Qwitter-DevOps?tab=readme-ov-file#aws)
- [Azure](https://github.com/Qwitter/Qwitter-DevOps?tab=readme-ov-file#azure)
- [Watchtower](https://github.com/Qwitter/Qwitter-DevOps?tab=readme-ov-file#watchtower)
- [ClouDNS](https://github.com/Qwitter/Qwitter-DevOps?tab=readme-ov-file#cloudns)

## Docker
Docker was used to containerize both the backend and frontend projects, making it easy to deploy them on hosted servers.
- [Backend Docker files](https://github.com/Qwitter/Qwitter-DevOps/tree/main/Backend/Docker)
- [Frontend Docker files](https://github.com/Qwitter/Qwitter-DevOps/tree/main/Frontend/Docker)

## Jenkins
Jenkins was employed to automate the process of pushing changes to GitHub. Instead of manually pulling these changes, building the Docker image, and then pushing it to Docker Hub, Jenkins handled the entire process automatically

In this project, I implemented a total of four pipelines: two for backend ([Development](https://github.com/Qwitter/Qwitter-DevOps/blob/main/Backend/Jenkins/Jenkinsfile_dev) and [Production](https://github.com/Qwitter/Qwitter-DevOps/blob/main/Backend/Jenkins/Jenkinsfile_prod)), and two for frontend ([Development](https://github.com/Qwitter/Qwitter-DevOps/blob/main/Frontend/Jenkins/Jenkinsfile_dev) and [Production](https://github.com/Qwitter/Qwitter-DevOps/blob/main/Frontend/Jenkins/Jenkinsfile_prod)).

Backend Development pipeline has the following stages:

![image](https://github.com/Qwitter/Qwitter-DevOps/assets/96792115/10a11c7f-d656-4d8d-9c2a-7090d50cd615)

Backend Production pipeline has the following stages:

![image](https://github.com/Qwitter/Qwitter-DevOps/assets/96792115/60d7dccd-5ff8-485b-981f-24eff5fd6f21)

Frontend Development pipeline has the following stages:

![image](https://github.com/Qwitter/Qwitter-DevOps/assets/96792115/1b91b49e-6335-4a36-b76f-23275c2cd1d2)

Frontend Production pipeline has the following stages:

![image](https://github.com/Qwitter/Qwitter-DevOps/assets/96792115/e0b472eb-75e2-4142-89c4-cc7ee83e7988)


I have also used a mailing service that sends an email to the team leader whenever a pipeline fails and when it returns to normal operation.

## Prometheus
Prometheus is an open-source monitoring tool tailored for dynamic infrastructures. With a robust querying language and alerting features, Prometheus enables real-time insights into system performance.
All Prometheus configuration files can be found [here](https://github.com/Qwitter/Qwitter-DevOps/tree/main/Monitoring).

## Grafana
Grafana is an open-source analytics and monitoring platform that integrates with Prometheus, allowing users to visualize and understand their metrics through dynamic and customizable dashboards. Its user-friendly interface and extensive plugin ecosystem make it a versatile tool for creating insightful and interactive visualizations to monitor and analyze data across different domains.

I have monitored my three servers: Backend, Frontend, and Jenkins.

![grafana1](https://github.com/Qwitter/Qwitter-DevOps/assets/96792115/805dd343-8266-43c2-9809-e16d16c6d775)
![grafana2](https://github.com/Qwitter/Qwitter-DevOps/assets/96792115/be073c9f-854d-4925-8448-9e4266286405)

# AWS
I utilized AWS to obtain a hosted relational database (RDS).

# Azure
I employed Azure to host the backend, frontend, and Jenkins, as well as to acquire Azure Storage for storing static files.

# Watchtower
Watchtower is an application that monitors running containers for changes to their images. When someone pushes an update to Docker Hub, Watchtower detects the changes, pulls down the new image, and subsequently restarts the container using the updated image with the same start options as the original.

# ClouDNS
I utilized clouDNS to obtain the domain name for Qwitter (qwitter.cloudns.org) and a sub-domain for the backend server (back.qwitter.cloudns.org).

## ©️Developers

| Name                 |         Email          |
|----------------------|:----------------------:|
| Fares Atef           | faresatef553@gmail.com |
