The pipeline supports parameterized deployments by allowing the user to select the target environment (dev, stg, or prod). Based on the selected environment, Jenkins automatically initializes Terraform, selects the appropriate Terraform workspace (or creates it if it doesn't already exist), and runs terraform plan using the corresponding .tfvars file.

After the planning stage, the pipeline pauses for a manual approval step before proceeding with the deployment. Once approved, Terraform applies the changes to the selected environment.

In addition, I configured post-build actions to send email notifications for both successful and failed pipeline executions, providing clear feedback about the deployment status.

This implementation demonstrates a complete CI/CD workflow using Jenkins and Terraform, including environment management, workspace automation, deployment approval, and notification handling.
