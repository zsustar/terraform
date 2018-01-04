###installation##
#download and unzip, and copy to some location like /usr/local/bin
#https://github.com/hashicorp/terraform/releases
#Go to https://www.terraform.io/downloads.html
wget https://releases.hashicorp.com/terraform/0.11.1/terraform_0.11.1_linux_amd64.zip
unzip terraform_*
sudo mv terraform /usr/local/bin/terraform
sudo chmod u+x /usr/local/bin/terraform

#Another Way, That will extract Terraform binary to /usr/local/bin, which is already available in PATH on Linux systems.
curl -O https://releases.hashicorp.com/terraform/0.8.2/terraform_0.8.2_linux_amd64.zip$> sudo unzip terraform_0.8.2_linux_amd64.zip -d /usr/local/bin/


#Terraform Best Practise
https://github.com/hashicorp/best-practices

#A best practice baseline Terraform repository containing Terraform scripts with the ability to deploy both compute and networking infrastructure into AWS, Microsoft Azure and Google Cloud Platform. 
https://github.com/contino/terraform-learn

#2 Years on AWS with Ansible, Terraform and Packer
https://www.agari.com/software-ate-infrastructure-2-years-aws-ansible-terraform-packer-part-1/
https://www.agari.com/software-ate-infrastructure-2-years-aws-ansible-terraform-packer-part-2/


#About Terraform

Terraform is an open source utility, created by the HashiCorp company, the same company that created Vagrant, Packer, Consul, and other popular infrastructure tools. It was initially released in July 2014, and since then, has come a long way to become one of the most important tools for infrastructure provisioning and management.

This is how Terraform is described by HashiCorp:

... a tool for safely and efficiently building, combining, and launching infrastructure. From physical servers to containers to SaaS products, Terraform is able to create and compose all the components necessary to run any service or application


"# terraform-aws299-invocare"

terraform plan -var-file="invocare_environment.tfvars" -var-file="provider-credentials.tfvars" -out="aws299.tfplan"
terraform apply aws299.tfplan


saga legend epic

# List State
terraform state list
# Print a complete state in a human-readable format:
terraform show
terraform state show aws_instance.hello-instance

#Modules
#Modules in Terraform are folders with Terraform files. 

############# AWS Provider ###############

1. # Static credentials
    provider "aws" {
        access_key = "xxxxxxxxxxxxx"
        secret_key = "xxxxxxxxxxxxx"
        region = "us-east-1"
    }

#Terraform Sequence
#在 Azure 中使用 Terraform 创建完整的 Linux 虚拟机基础结构
https://docs.microsoft.com/zh-cn/azure/virtual-machines/linux/terraform-create-complete-vm
1. 第一步是初始化 Terraform。 此步骤可确保 Terraform 具有你要在 Azure 中生成模板的所有必备组件。
  #terraform init。 此命令将下载创建 Azure 资源组所需的 Azure 模块
2. 让 Terraform 检查并验证模板。 此步骤将请求的资源与 Terraform 保存的状态信息进行比较，然后输出计划的执行。 资源不是在 Azure 中创建的。
  # terraform plan

  
#TFLint: TFLint is a Terraform linter for detecting errors that can not be detected by terraform plan
https://github.com/wata727/tflint

#
Terraform的模板由几大结构组成：
 1. 资源(resource)、
 2. 变量(variable)、
 3. 输出(output)，
 4. 数据源(data)
  quote link: https://www.terraform.io/docs/providers/aws/d/ami.html
  
 
 Terraform VPC
 https://github.com/melbourneit-es/terraform-aws-vpc?ref=v0.4
 
Null Resource   
 triggers - (Optional) A map of arbitrary strings that, when changed, will force the null resource to be replaced, re-running any associated provisioners. 
 
