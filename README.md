# Express App

This repository contains the express-app used for Exercise 3.1 (Deployment Pipelines) of the DevOps with Docker course.

## Original Source
The original codebase was obtained from:

https://github.com/docker-hy/material-applications/tree/main/express-app

which is part of the docker-hy/material-applications repository.

## Course Reference

This project is used as part of the solution for:

Exercise 3.1 – Deployment Pipelines

DevOps with Docker, Fall 2026 (MOOC.fi)

https://courses.mooc.fi/org/uh-cs/courses/devops-with-docker-fall-2026/chapter-4/deployment-pipelines

## Notes

The original application code was provided by the course materials. This repository contains the work for completing the exercise requirements, including Docker image build and deployment pipeline configuration.

## Container Access

Access with browser http://localhost:8080


## How to run

1. build the express.js image by ```docker build -t express-app .```

2. confirm the image is successfully built by ``` docker image ls express-app```

3. run the docker image by ```docker run -d -p 8080:8080 --name express-container express-app```

4. confirm the container is running by ```docker ps```


---
<small>Date : Oct 31 2026</small>