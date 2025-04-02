# Week 1: Terraform Essentials - Class 2: Terraform State, Variables, and Providers

## 🎯 Goal: Understand Terraform state, use variables, and work with multiple cloud providers.

---

## 1️⃣ What is Terraform State?

Terraform uses a **state file** (typically named `terraform.tfstate`) to keep track of the resources it is managing. This file is essential for Terraform to:

✅ **Keep track of what Terraform has deployed:** It records metadata about the infrastructure that has been successfully created.

✅ **Understand what needs to be updated or deleted:** When you run Terraform, it compares your configuration with the state file to determine the necessary changes.

✅ **Should be stored securely:** The state file can contain sensitive information and should be stored in a secure remote backend such as AWS S3, Terraform Cloud, or Azure Blob Storage.

### 🔍 Checking Terraform State

After you have applied your Terraform configuration, you can inspect the current state using the `terraform show` command:

```bash
terraform show

This command will display the current state of your managed infrastructure in a human-readable format.

⚠️ Warning: Do NOT manually edit the .tfstate file!
Modifying the state file directly can lead to inconsistencies and errors in your infrastructure management. Always let Terraform manage the state through its commands.

2️⃣ Using Terraform Variables
Variables in Terraform allow you to create more flexible and reusable configurations. They act as placeholders for values that can be easily changed without modifying the main configuration code.

📄 Define a Variable (variables.tf)
It's common practice to define variables in a file named variables.tf. Create this file in your Terraform project directory and add a variable definition like this:

variable "instance_type" {
  description = "Type of AWS instance"
  type        = string
  default     = "t2.micro"
}

1 variable "instance_type": Declares a variable named instance_type.
2 description: Provides a helpful explanation of the variable's purpose.
3 type: Specifies the expected data type of the variable (e.g., string, number, bool).
4 default: Sets a default value for the variable. If no other value is provided, this will be used.

📄 Use the Variable in main.tf
Now, modify your main.tf file to use the instance_type variable:

resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = var.instance_type
}

Here, var.instance_type references the value of the instance_type variable.

🛠 Assigning Values to Variables
You can assign values to Terraform variables in several ways:

1️⃣ Using terraform.tfvars file
Create a file named terraform.tfvars in your Terraform project directory. Terraform automatically loads this file and applies the variable values defined within it.

# terraform.tfvars
instance_type = "t3.micro"

2️⃣ Using Command-Line Interface (CLI)
You can use the -var flag with Terraform commands like apply to specify variable values directly:

terraform apply -var="instance_type=t3.micro"

Markdown

# Week 1: Terraform Essentials - Class 2: Terraform State, Variables, and Providers

## 🎯 Goal: Understand Terraform state, use variables, and work with multiple cloud providers.

---

## 1️⃣ What is Terraform State?

Terraform uses a **state file** (typically named `terraform.tfstate`) to keep track of the resources it is managing. This file is essential for Terraform to:

✅ **Keep track of what Terraform has deployed:** It records metadata about the infrastructure that has been successfully created.

✅ **Understand what needs to be updated or deleted:** When you run Terraform, it compares your configuration with the state file to determine the necessary changes.

✅ **Should be stored securely:** The state file can contain sensitive information and should be stored in a secure remote backend such as AWS S3, Terraform Cloud, or Azure Blob Storage.

### 🔍 Checking Terraform State

After you have applied your Terraform configuration, you can inspect the current state using the `terraform show` command:

```bash
terraform show
This command will display the current state of your managed infrastructure in a human-readable format.

⚠️ Warning: Do NOT manually edit the .tfstate file!
Modifying the state file directly can lead to inconsistencies and errors in your infrastructure management. Always let Terraform manage the state through its commands.

2️⃣ Using Terraform Variables
Variables in Terraform allow you to create more flexible and reusable configurations. They act as placeholders for values that can be easily changed without modifying the main configuration code.

📄 Define a Variable (variables.tf)
It's common practice to define variables in a file named variables.tf. Create this file in your Terraform project directory and add a variable definition like this:

Terraform

variable "instance_type" {
  description = "Type of AWS instance"
  type        = string
  default     = "t2.micro"
}
variable "instance_type": Declares a variable named instance_type.
description: Provides a helpful explanation of the variable's purpose.
type: Specifies the expected data type of the variable (e.g., string, number, bool).
default: Sets a default value for the variable. If no other value is provided, this will be used.
📄 Use the Variable in main.tf
Now, modify your main.tf file to use the instance_type variable:

Terraform

resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = var.instance_type
}
Here, var.instance_type references the value of the instance_type variable.

🛠 Assigning Values to Variables
You can assign values to Terraform variables in several ways:

1️⃣ Using terraform.tfvars file
Create a file named terraform.tfvars in your Terraform project directory. Terraform automatically loads this file and applies the variable values defined within it.

Terraform

# terraform.tfvars
instance_type = "t3.micro"
2️⃣ Using Command-Line Interface (CLI)
You can use the -var flag with Terraform commands like apply to specify variable values directly:

Bash

terraform apply -var="instance_type=t3.micro"
3️⃣ Using Environment Variables
Terraform can also read variable values from environment variables. The environment variable name must be prefixed with TF_VAR_ followed by the name of the Terraform variable.

On Linux/macOS:

export TF_VAR_instance_type="t3.micro"
terraform apply

On Windows (Command Prompt):

set TF_VAR_instance_type="t3.micro"
terraform apply

On Windows (PowerShell):

$env:TF_VAR_instance_type = "t3.micro"
terraform apply

3️⃣ Working with Multiple Providers
Terraform's power comes from its ability to manage resources across various cloud providers and services. To work with multiple providers, you configure the necessary provider blocks in your Terraform configuration.

Example: Switching to Azure
To manage resources in Microsoft Azure, you would configure the azurerm provider. Add the following to your main.tf (or a separate .tf file):

provider "azurerm" {
  features {}
}

resource "azurerm_resource_group" "example" {
  name     = "terraform-rg"
  location = "East US"
}

provider "azurerm": Configures the AzureRM provider. The features {} block is often required for AzureRM.

resource "azurerm_resource_group" "example": Defines an Azure Resource Group.

Initializing for Multiple Providers
When you add or change providers in your Terraform configuration, you need to re-initialize your Terraform project to download the necessary provider plugins:

terraform init

Markdown

# Week 1: Terraform Essentials - Class 2: Terraform State, Variables, and Providers

## 🎯 Goal: Understand Terraform state, use variables, and work with multiple cloud providers.

---

## 1️⃣ What is Terraform State?

Terraform uses a **state file** (typically named `terraform.tfstate`) to keep track of the resources it is managing. This file is essential for Terraform to:

✅ **Keep track of what Terraform has deployed:** It records metadata about the infrastructure that has been successfully created.

✅ **Understand what needs to be updated or deleted:** When you run Terraform, it compares your configuration with the state file to determine the necessary changes.

✅ **Should be stored securely:** The state file can contain sensitive information and should be stored in a secure remote backend such as AWS S3, Terraform Cloud, or Azure Blob Storage.

### 🔍 Checking Terraform State

After you have applied your Terraform configuration, you can inspect the current state using the `terraform show` command:

```bash
terraform show
This command will display the current state of your managed infrastructure in a human-readable format.

⚠️ Warning: Do NOT manually edit the .tfstate file!
Modifying the state file directly can lead to inconsistencies and errors in your infrastructure management. Always let Terraform manage the state through its commands.

2️⃣ Using Terraform Variables
Variables in Terraform allow you to create more flexible and reusable configurations. They act as placeholders for values that can be easily changed without modifying the main configuration code.

📄 Define a Variable (variables.tf)
It's common practice to define variables in a file named variables.tf. Create this file in your Terraform project directory and add a variable definition like this:

Terraform

variable "instance_type" {
  description = "Type of AWS instance"
  type        = string
  default     = "t2.micro"
}
variable "instance_type": Declares a variable named instance_type.
description: Provides a helpful explanation of the variable's purpose.
type: Specifies the expected data type of the variable (e.g., string, number, bool).
default: Sets a default value for the variable. If no other value is provided, this will be used.
📄 Use the Variable in main.tf
Now, modify your main.tf file to use the instance_type variable:

Terraform

resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = var.instance_type
}
Here, var.instance_type references the value of the instance_type variable.

🛠 Assigning Values to Variables
You can assign values to Terraform variables in several ways:

1️⃣ Using terraform.tfvars file
Create a file named terraform.tfvars in your Terraform project directory. Terraform automatically loads this file and applies the variable values defined within it.

Terraform

# terraform.tfvars
instance_type = "t3.micro"
2️⃣ Using Command-Line Interface (CLI)
You can use the -var flag with Terraform commands like apply to specify variable values directly:

Bash

terraform apply -var="instance_type=t3.micro"
3️⃣ Using Environment Variables
Terraform can also read variable values from environment variables. The environment variable name must be prefixed with TF_VAR_ followed by the name of the Terraform variable.

On Linux/macOS:

Bash

export TF_VAR_instance_type="t3.micro"
terraform apply
On Windows (Command Prompt):

Bash

set TF_VAR_instance_type="t3.micro"
terraform apply
On Windows (PowerShell):

PowerShell

$env:TF_VAR_instance_type = "t3.micro"
terraform apply
3️⃣ Working with Multiple Providers
Terraform's power comes from its ability to manage resources across various cloud providers and services. To work with multiple providers, you configure the necessary provider blocks in your Terraform configuration.

Example: Switching to Azure
To manage resources in Microsoft Azure, you would configure the azurerm provider. Add the following to your main.tf (or a separate .tf file):

Terraform

provider "azurerm" {
  features {}
}

resource "azurerm_resource_group" "example" {
  name     = "terraform-rg"
  location = "East US"
}
provider "azurerm": Configures the AzureRM provider. The features {} block is often required for AzureRM.
resource "azurerm_resource_group" "example": Defines an Azure Resource Group.
Initializing for Multiple Providers
When you add or change providers in your Terraform configuration, you need to re-initialize your Terraform project to download the necessary provider plugins:

Bash

terraform init
Terraform will detect the new provider configuration and download the azurerm provider plugin (in addition to any other configured providers).

🎯 What You Learned
✅ Understood what Terraform state is and why it is crucial for managing infrastructure.

✅ Learned how to define and use Terraform variables to make your configurations more flexible.

✅ Explored different ways to assign values to Terraform variables: terraform.tfvars files, command-line flags, and environment variables.

✅ Got an introduction to working with multiple cloud providers by configuring provider blocks and initializing Terraform.

🚀 Next Class: Terraform Modules & Workspaces
🎯 Goal: Learn how to create reusable modules and manage multiple environments with workspaces.


