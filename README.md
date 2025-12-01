# Deploy Nginx on EC2 instance using the user's own Terraform modules

Deploy a modular, reusable Nginx infrastructure using Terraform on AWS. This repository demonstrates best practices in infrastructure-as-code (IaC), enabling scalable, maintainable deployments with the aid of Terraform modules.

## Features

- Modular design: Each infrastructure component (network, server, security groups, etc.) is implemented as a separate Terraform module.
- Parameterised deployment: Flexible configuration using variables.
- Outputs for seamless integration.
- Example deployment files provided.


## Prerequisites

- Terraform
- AWS account and credentials with permissions to create resources

## Usage

1. Clone the repository:
    ```sh
    git clone https://github.com/btilki/Deploy-a-web-server-using-Terraform-module.git
    cd Deploy-a-web-server-using-Terraform-module
    ```

2. Initialize Terraform:
    ```sh
    terraform init
    ```

3. Review and adjust variables:
    - Edit `variables.tf` for custom values or set them via `terraform.tfvars`

4. Plan infrastructure:
    ```sh
    terraform plan
    ```

5. Deploy infrastructure:
    ```sh
    terraform apply
    ```
    Confirm when prompted.

6. Destroy infrastructure (when finished):
    ```sh
    terraform destroy
    ```

## Module Examples

Below is a sample of how a module is called in `main.tf`:

```hcl
module "web_server" {
  source = "./modules/web-server"
  instance_type = var.instance_type
  ami_id        = var.ami_id
  ...
}
```

## Outputs

After deployment, useful information such as public IPs and DNS names are available in the output.


## License

MIT License
