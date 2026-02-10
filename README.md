## Node.js CI/CD Deployment using GitHub Actions & EC2
This project demonstrates a simple but complete CI/CD pipeline where a Node.js application is automatically deployed to an AWS EC2 instance whenever code is pushed to the main branch.

### Project Overview
- Node.js + Express server
- Hosted on an AWS EC2 instance
- GitHub Actions used for CI/CD 
- Automatic deployment on every git push
- Live version update verification (v1 → v2)

### CI/CD Workflow Explanation
#### Code Push to GitHub

Whenever code is pushed to the main branch:
```
git add .
git commit -m "changed to v2 --> update"
git push origin main
```
![alt text](/outputs/image.png)

#### GitHub Actions Triggered
- The push triggers the GitHub Actions workflow defined in:
`.github/workflows/deploy.yml`
The workflow:

- Checks out the repository

- Connects to the EC2 instance using SSH

- Pulls the latest code

- Restarts the Node.js application

![alt text](/outputs/image-1.png)

### Workflow Execution
The deployment job runs successfully on GitHub-hosted runners.

![alt text](/outputs/image-2.png)

### Application Running on EC2 (v1)
Before update, the server responds with:
![alt text](/outputs/image-3.png)
This confirms the initial deployment is working.

### Live Update After Deployment (v2)
After pushing updated code, the live application reflects the change without any manual intervention.

![alt text](/outputs/image-4.png)

This confirms successful CI/CD automation.

### Secrets Used
The following secrets are configured in GitHub repository settings:
![alt text](/outputs/image-5.png)