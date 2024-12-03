# primeiro precisamos baixar o azure-cli
> `az login` para fazer login

checando a documentação sempre em `@terraform-registry`

a primeira versão fica mais ou menos assim:
``` terraform
terraform {
  required_providers {
    azurerm = {
      source = "hashicorp/azurerm"
      version = "4.12.0"
    }
  }
}

provider "azurerm" {
    features {}
}

resource "azurerm_resource_group" "example" {
  name     = "rg-terraform"
  location = "East US"
}
```

> Depois precisamos fazer no terminal: `terraform init`
