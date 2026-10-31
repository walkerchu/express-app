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

1. pull the latest express.js image from Docker Hub by ```docker pull walkerchu/express-app:latest```

2. confirm the image is tagged as 'latest' by ```docker image ls walkerchu/express-app```

3. run the docker image by ```docker run -d -p 8080:8080 --name express-container walkerchu/express-app:latest```

4. confirm the container is running by ```docker ps```

5. start Watchtower container by ```docker compose up -d```

6. execute ```docker ps``` again to confirm both express.js and Watchtower containers are running

7. modify `index.js`, commit the change, and push to GitHub

8. upon GitHub Actions run successfully, new docker image will be pushed to Docker Hub

9. go to https://hub.docker.com/repository/docker/walkerchu/express-app/image-management and check the 'Digest' of latest image. If the digest differs from the previous value, a new image has been successfully pushed to Docker Hub.

10. observe Watchtower log shown in Linux terminal (or execute ```docker logs watchtower``` to display the logs)

11. If Watchtower detects a newer image, the following messages will appear in the logs:

    ```
    watchtower  | time=2026-10-31T20:52:41Z level=info msg="Found new image" container=express-container image=walkerchu/express-app:latest new_id=523223fd7b25
    
    watchtower  | time=2026-10-31T20:52:41Z level=info msg="Stopping container" container=express-container id=09b0b329dfd3 signal=SIGTERM timeout=30000
    
    watchtower  | time=2026-10-31T20:53:11Z level=info msg="Started new container" container=express-container image=walkerchu/express-app:latest new_id=19acf06045ff
    ```

---
<small>Date : Oct 31 2026</small>