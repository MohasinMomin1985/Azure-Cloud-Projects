# Azure-Cloud-Projects:

## Project -01 : CI/CD Pipeline for a .NET Core Application Using Azure DevOps

### 1. Project Scope
This project focuses on setting up a Continuous Integration and Continuous Deployment (CI/CD) pipeline for a .NET Core web application using Azure DevOps. The pipeline automates code integration, testing, and deployment to Azure App Service. The goal is to ensure fast, reliable, and automated software delivery with minimal manual intervention.

### Key Features:
● Automated build and testing of the application
● Deployment to Azure App Service
● Versioning control and rollback mechanism
● Integration with Azure DevOps Repos and GitHub

### 2. Tools Used
● Azure DevOps – For managing repositories, pipelines, and releases
● Azure Repos or GitHub – Source code version control
● Azure Pipelines – CI/CD automation
● Azure App Service – Hosting the application
● MSTest / NUnit – For unit testing
● SonarCloud – Code quality and security analysis
● Azure Key Vault – Secure management of secrets
● Application Insights – Performance monitoring

### 3. Analysis Approach
Current Challenges Without CI/CD
● Manual deployments are time-consuming and error-prone
● Lack of automated testing can lead to undetected issues in production
● Security vulnerabilities due to hardcoded credentials
Proposed Solution
Implement a fully automated CI/CD pipeline to handle build, testing, security scanning, and deployment seamlessly.

### Pipeline Flow:
1. Developer commits code to Azure Repos/GitHub.
2. Azure Pipelines triggers build and runs tests.
3. SonarCloud performs static code analysis.
4. Security scanning using Azure Key Vault to fetch secrets.
5. If all tests pass, the build artifact is stored in Azure Artifacts.
6. Azure Pipelines deploys the application to Azure App Service.
7. Application Insights provides monitoring and logs.
4. Step-by-Step Implementation

#### Step 1: Set Up Azure DevOps Repository
1. Go to Azure DevOps and create a new project.
2. Navigate to Repos → Import Code or clone a new repository.
3. Use the following Git commands to push an existing .NET Core app:

    <img width="337" height="117" alt="Screenshot 2026-05-21 at 1 38 16 AM" src="https://github.com/user-attachments/assets/43d537fc-750d-4909-9ca9-d82bd1ca141f" />


#### Step 2: Create a CI Pipeline in Azure DevOps
1. Go to Pipelines → New Pipeline → Choose Azure Repos Git or GitHub.
Select Starter Pipeline and replace it with this YAML:

    <img width="559" height="522" alt="Screenshot 2026-05-21 at 1 45 58 AM" src="https://github.com/user-attachments/assets/8ba86ed9-8a4c-4be8-8f77-63a408b24e8a" />


2. Save and run the pipeline to build and test the application.

#### Step 3: Integrate SonarCloud for Code Quality
1. Go to SonarCloud and create an account.
2. Connect it to Azure DevOps and set up a new project.
Modify the pipeline to include:

    <img width="557" height="298" alt="Screenshot 2026-05-21 at 1 46 47 AM" src="https://github.com/user-attachments/assets/71cb5893-cff7-4834-b675-a7e546306b56" />


#### Step 4: Set Up CD Pipeline to Azure App Service
1. Go to Releases → New Release Pipeline.
2. Choose Azure App Service Deployment template.
3. Select Azure Subscription and the App Service name.
4. Choose the drop artifact from CI pipeline.
5. Configure deployment stages like Staging and Production.
6. Enable Approval Gates for manual approvals before production deployment.
7. Click Create Release and deploy.

#### Step 5: Secure Secrets Using Azure Key Vault
1. In Azure Portal, go to Key Vault → Create a new vault.
2. Add a secret (e.g., DatabaseConnectionString).
In Azure Pipelines, add the Azure Key Vault task:

    <img width="627" height="171" alt="Screenshot 2026-05-21 at 1 48 01 AM" src="https://github.com/user-attachments/assets/da54e6e7-46a5-4535-bd58-b344ec7d7305" />


#### Step 6: Monitor Using Application Insights
1. In Azure Portal, navigate to Application Insights and link it to the app.
Modify appsettings.json:

  <img width="756" height="110" alt="Screenshot 2026-05-21 at 1 49 37 AM" src="https://github.com/user-attachments/assets/f6c4a1f9-62f1-4d5d-a07e-bac119276904" />

 
3. Update the Azure DevOps release pipeline to enable monitoring logs.
5. Conclusion

#### This project successfully implemented an end-to-end CI/CD pipeline for a .NET Core web application using Azure DevOps. 

#### Key benefits:
✅ Automated Build & Testing – Ensuring high code quality 

✅ Faster Deployment – Reducing manual intervention 

✅ Secure Configuration Management – Using Azure Key Vault 

✅ Monitoring & Logging – With Application Insights

#### Real-Time Example:
A software company developing a finance dashboard can use this pipeline to deploy new features faster while ensuring security and stability.
