# End-to-End CI/CD Pipeline for Node.js using Jenkins & Docker

This repository contains a **fully working Node.js project** with an **end-to-end CI/CD pipeline** using **GitHub, Jenkins, and Docker**.

This is not a demo-only repo. The pipeline builds successfully, creates a Docker image, runs a container, and exposes the application on **port 3000**.

---

## What this project does (no nonsense)

* Hosts a simple Node.js server
* Push to GitHub triggers Jenkins pipeline
* Jenkins installs dependencies
* Jenkins builds a Docker image
* Jenkins runs the Docker container
* Application becomes accessible via browser

If any of this is unclear to you, you need more hands-on practice.

---

## Tech stack used

* Node.js
* Docker
* Jenkins (Declarative Pipeline)
* GitHub

---

## Project structure

```
Node.js-pipeline/
│── .gitignore
│── Dockerfile
│── Jenkinsfile
│── package.json
│── package-lock.json
│── server.js
│── README.md
```

This structure matters. Change it randomly and your pipeline will fail.

---

## Prerequisites

You **must** have the following installed:

* Git
* Docker
* Jenkins (with Docker permission)
* Node.js (for local testing)

No Docker or Jenkins = no CI/CD. Period.

---

## Run the project locally (without Jenkins)

```bash
git clone https://github.com/vikkram-devops-engineer/Node.js-pipeline.git
cd Node.js-pipeline
npm install
node server.js
```

Access the app:

```
http://localhost:3000
```

---

## Run the project using Docker

```bash
docker build -t node-ci-cd .
docker run -d -p 3000:3000 node-ci-cd
```

Open browser:

```
http://<your-ip>:3000
```

---

## Jenkins CI/CD Pipeline flow

1. **Checkout** code from GitHub
2. **Install dependencies** using npm
3. **Build Docker image**
4. **Stop & remove old container (if exists)**
5. **Run new Docker container**

Pipeline logic is defined inside the `Jenkinsfile`. If you configure everything in Jenkins UI instead of Jenkinsfile, you are doing CI/CD wrong.

---

## Successful output (this is how you verify)

* Jenkins job status shows **SUCCESS**
* Docker image visible using `docker images`
* Running container visible using `docker ps`
* App reachable at:

```
http://<Jenkins-host-IP>:3000
```

If any of these fail, your pipeline is not successful.

---

## Common mistakes (don’t blame Jenkins)

* Jenkins user does not have Docker permission
* Port 3000 already in use
* Old container not removed
* Wrong GitHub repo URL

These are setup issues, not tool problems.

---

## Author

**Vikkram S K**
DevOps Engineer (AWS | CI/CD | Jenkins | Docker)

---

## Final note

This repository proves that you can build a real CI/CD pipeline, not just talk about it.
If you cannot explain every step here, stop copying code and start understanding it.
