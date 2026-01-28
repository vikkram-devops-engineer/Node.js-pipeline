# Node.js CI/CD Pipeline with Jenkins & Docker

This repository contains a **basic but complete CI/CD pipeline** for a Node.js application using **Jenkins** and **Docker**. No fluff. Just the essentials that actually work.

---

## What this project does

* Pulls Node.js source code from GitHub
* Installs dependencies
* Builds a Docker image
* Runs the application inside a Docker container
* Exposes the app on **port 3000**

If you don’t understand these steps, you’re not ready for DevOps interviews yet. Fix that before adding buzzwords.

---

## Tech stack

* **Node.js**
* **Docker**
* **Jenkins (Declarative Pipeline)**
* **GitHub**

---

## Project structure

```
Node.js-pipeline/
│── Jenkinsfile
│── Dockerfile
│── package.json
│── package-lock.json
│── app.js
│── README.md
```

If your structure doesn’t look like this, your pipeline will break. Simple.

---

## Prerequisites

You must have these installed **before** running anything:

* Node.js (v18+ recommended)
* Docker
* Jenkins
* Git

No Docker, no pipeline. Period.

---

## Jenkins pipeline stages

1. **Checkout** – Pull code from GitHub
2. **Install Dependencies** – `npm install`
3. **Build Docker Image**
4. **Run Docker Container**

Pipeline is defined in the `Jenkinsfile`. If Jenkins UI config is doing the work instead of the file, you’re doing CI/CD wrong.

---

## How to run locally (without Jenkins)

```bash
npm install
node app.js
```

App will be available at:

```
http://localhost:3000
```

---

## How to run using Docker

```bash
docker build -t node-ci-cd .
docker run -d -p 3000:3000 node-ci-cd
```

Check in browser:

```
http://<your-ip>:3000
```

---

## Common mistakes (read this before blaming tools)

* Forgetting to expose port 3000 in Dockerfile
* Jenkins user not having Docker permissions
* Wrong repo URL in Jenkins job
* Old container already running on same port

These are **user mistakes**, not Jenkins issues.

---

## Author

**Vikkram S K**
DevOps Engineer (AWS | CI/CD | Docker | Jenkins)

---

## Final note

This repo is intentionally simple. If you can’t explain every line here, stop copying pipelines from YouTube and start learning fundamentals.


