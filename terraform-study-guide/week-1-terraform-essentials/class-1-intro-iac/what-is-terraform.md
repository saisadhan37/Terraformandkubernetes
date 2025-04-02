# Week 1: Terraform Essentials - Class 1: Introduction to Terraform & Infrastructure as Code

## 🎯 Goal: Understand the basics of Terraform, install it, and deploy your first infrastructure.

---

## 1️⃣ What is Terraform?

Terraform is an **Infrastructure as Code (IaC)** tool by HashiCorp that allows you to define and manage infrastructure in a **declarative** way. It helps you automate cloud deployments instead of manually setting up resources.

## 🚀 Why Use Terraform?

✅ **Multi-Cloud Support:** Works with various providers like AWS, Azure, GCP, Kubernetes, and more.

✅ **Declarative Configuration:** You define the desired state of your infrastructure ("what" you need), and Terraform figures out the steps ("how") to achieve it.

✅ **Idempotent Execution:** Applying the same Terraform configuration multiple times will result in the same infrastructure state. Terraform will only make changes if necessary.

✅ **Version Control Friendly:** Your infrastructure is defined in code, making it easy to manage with Git for version history, collaboration, and integration with CI/CD pipelines.

---

## 2️⃣ Install Terraform

### 🔧 Step 1: Install Terraform on Your System

Terraform can be installed on Linux, Mac, and Windows using the following methods:

###################################

 🔹 Windows (via Chocolatey)

   choco install terraform

🔹 Mac (via Homebrew)
  brew tap hashicorp/tap
  brew install hashicorp/tap/terraform
  
🔹 Linux (via apt)
   sudo apt-get update && sudo apt-get install -y terraform
   
✅ Verify Installation

After installation, verify that Terraform is correctly installed by running the following command in your terminal:


terraform -version
You should see output similar to this (the version number might be different):

Terraform v1.5.0

##################################

3️⃣ Writing Your First Terraform Configuration
Now, let's deploy a simple AWS EC2 instance using Terraform.

📄 Create a Terraform File (main.tf)
Create a new directory for your Terraform project and navigate into it:

 mkdir terraform-project && cd terraform-project

Create an empty file named main.tf:

Bash

touch main.tf
Edit the main.tf file using a text editor and add the following configuration:

Terraform

provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0" # Amazon Linux 2 AMI
  instance_type = "t2.micro"
}
provider "aws": This block configures the AWS provider, which allows Terraform to interact with your AWS account.
region = "us-east-1": Specifies the AWS region where the resources will be created.
resource "aws_instance" "example": This block defines an AWS EC2 instance resource.
"aws_instance": The type of AWS resource to create.
"example": A local name you give to this resource within your Terraform configuration.
ami = "ami-0c55b159cbfafe1f0": The Amazon Machine Image (AMI) ID to use for the instance (Amazon Linux 2 in this case).
instance_type = "t2.micro": The instance type for the EC2 instance.

4️⃣ Running Terraform Commands
Now, let's initialize and apply the configuration:

🛠️ Step 1: Initialize Terraform
Run the following command in your terraform-project directory:

Bash

terraform init
This command initializes the Terraform working directory. It downloads and installs the AWS provider plugin (because you've specified provider "aws" in your main.tf file).

🛠️ Step 2: Plan the Changes
Next, run the terraform plan command:

Bash

terraform plan
Terraform analyzes your configuration and compares it to the current state (which is empty initially). It then generates an execution plan, showing you exactly what resources will be created, modified, or destroyed. This is a good way to preview the changes before applying them.

🛠️ Step 3: Apply the Configuration
To actually create the infrastructure defined in your main.tf file, run the terraform apply command:

Bash

terraform apply
Terraform will present the execution plan again and ask for your confirmation. Type yes and press Enter to proceed with the creation of the EC2 instance.

🛠️ Step 4: Destroy the Resources
Once you're done experimenting and want to remove the created infrastructure, run the terraform destroy command:

Bash

terraform destroy
Terraform will again show you a plan of what will be destroyed and ask for confirmation. Type yes and press Enter to terminate the EC2 instance.

🎯 What You Learned
✅ Installed Terraform successfully on your system.

✅ Wrote your first Terraform configuration file (main.tf) to define an AWS EC2 instance.

✅ Used the essential Terraform commands:
* terraform init: To initialize the working directory and download providers.
* terraform plan: To preview the changes Terraform will make.
* terraform apply: To create or modify the infrastructure.
* terraform destroy: To remove the created infrastructure.

✅ Deployed an AWS EC2 instance using Terraform.

