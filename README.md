# Maven CI with GitHub Actions

This project demonstrates setting up Continuous Integration (CI) for a Maven project using GitHub Actions, along with Docker image creation and push to Docker Hub.

## Steps

1. Go to **Actions** in your GitHub repository and select **Configure with Maven**.
2. The boilerplate code will checkout the current repository.
3. The maven will be configured and also will package the application into a jar file.
4. Create a Docker image using the provided `Dockerfile`.
5. Push the Docker image to Docker Hub using login credentials provided through GitHub **Variables** and **Secrets**.

## How to See it in Action

1. Push to the `main` branch or create a pull request targeting the `main` branch.
2. The workflow will automatically trigger and execute the build and deployment process.

---

Feel free to fork the repo and try it yourself!

