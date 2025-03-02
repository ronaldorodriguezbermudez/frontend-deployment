# Frontend Deployment

This project is a simple frontend application designed to be deployed on an Nginx server running on an EC2 instance. Below are the details regarding the project structure, setup instructions, and deployment process.

## Project Structure

```
frontend-deployment
├── src
│   ├── index.html      # Main HTML file for the frontend application
│   ├── styles.css      # Styles for the frontend application
│   └── app.js          # JavaScript code for client-side logic
├── .github
│   └── workflows
│       └── deploy.yml  # GitHub Actions workflow for continuous deployment
├── package.json        # Configuration file for npm
├── README.md           # Documentation for the project
└── nginx.conf          # Nginx server configuration
```

## Setup Instructions

1. **Clone the Repository**: 
   Clone this repository to your local machine using:
   ```
   git clone <repository-url>
   ```

2. **Install Dependencies**: 
   Navigate to the project directory and install the necessary dependencies using npm:
   ```
   npm install
   ```

3. **Modify Nginx Configuration**: 
   Update the `nginx.conf` file as needed to suit your deployment requirements.

## Deployment

This project uses GitHub Actions for continuous deployment. The deployment process is defined in the `.github/workflows/deploy.yml` file. 

### Steps in the Deployment Workflow:

1. Connect to the EC2 instance via SSH using the PEM file stored as a GitHub secret.
2. Install Nginx on the EC2 instance if it is not already installed.
3. Copy the frontend files from the repository to the appropriate directory on the EC2 instance.
4. Start or reload the Nginx service to serve the frontend application.

Make sure to configure your GitHub repository secrets to include the necessary PEM file for SSH access.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.