# Maven-CI-with-Github-Actions

Steps
1. Go to actions and select configure with Maven.
2. Fetch from the Maven Repo.
3. Build the jar file
4. Create docker image using Dockerfile.
5. Push the image to Dockerhub via login credentials provided through variables and secrets.

How to see in action
1. Push to the main branch or create a pull request to the main branch.
2. The workflow automatically starts executing.
