# Project Title

## Description
This project showcases a robust CI/CD pipeline using GitHub Actions to manage the build and deployment process of a Java project utilizing Maven. A Docker image is created and published to JFrog Artifactory, with an Xray scan conducted to ensure the integrity and security of the build.

## Workflow Files
### 1. Java CI with Maven:
   - Triggered on push or pull requests to the main branch.
   - Sets up JDK and builds the project using Maven Wrapper.

### 2. Build and Publish to JFrog Artifactory:
   - Triggered on push to the main branch.
   - Sets up JDK, compiles and tests the code.
   - Builds a Docker image and sets up JFrog CLI.
   - Tags and pushes Docker image to JFrog Artifactory.
   - Publishes build info to JFrog Artifactory.
   - Conducts an Xray scan on the build.

## GitHub Actions Usage
- Code changes in the main branch or pull requests will automatically trigger the corresponding workflow.
- View the workflow progress and logs under the Actions tab in your GitHub repository.

## Setup GitHub Secrets
Setup the following secrets in your GitHub repository to allow interaction with JFrog Artifactory:
- `JF_URL`: Your JFrog instance URL.
- `JF_ACCESS_TOKEN`: Your JFrog Access Token for authentication.

## Local Development
Clone the repository and execute Maven commands for building and testing locally before pushing changes to the repository.

```bash
git clone <repository-url>
cd <repository-directory>
./mvnw clean package
