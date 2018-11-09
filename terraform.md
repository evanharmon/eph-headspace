# TERRAFORM

## Installation
[Getting Started](https://www.terraform.io/intro/getting-started/install.html)

Steps:
* [Download](https://www.terraform.io/downloads.html) terraform in to the
`$HOME/Downloads` folder

* Make a directory, unzip / copy the binary
```console
mkdir $HOME/bin
unzip $HOME/Downloads/terraform_0.11.8_darwin_amd64.zip -d $HOME/bin
```

* Add the below line to your `.bashrc, .bash_profile, .zshrc` file
```shell
export PATH=$HOME/bin:$PATH
```

## Documentation
[AWS](https://www.terraform.io/docs/providers/aws/index.html)

## Tutorials / Learning
[Best Course - Learn DevOps: Infrastructure Automation With Terraform](https://www.udemy.com/learn-devops-infrastructure-automation-with-terraform/learn/v4/content)

## Examples
[Gruntwork Introduction to Terraform](https://blog.gruntwork.io/an-introduction-to-terraform-f17df9c6d180)
[Terraform AWS Modules](https://github.com/terraform-aws-modules)

## Functions
### cidrsubnet
[Article](http://blog.itsjustcode.net/blog/2017/11/18/terraform-cidrsubnet-deconstructed/)

### Route Table Associations
[Count](https://stackoverflow.com/questions/51739482/terraform-how-to-associate-multiple-subnet-to-route-table)
