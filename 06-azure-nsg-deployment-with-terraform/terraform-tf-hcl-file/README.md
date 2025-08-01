# Deploy a Network Security Group with Inbound/Outbound Rules 
- Create a .tf file using the code and edit it before saving and uploading to the CLI.

```hcl
terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "=3.0.0"
    }
  }
}

# Configure the Microsoft Azure Provider
provider "azurerm" {
  features {}

  skip_provider_registration = true
}

resource "azurerm_network_security_group" "nsg" {
  name                = "LabNSG"
  location            = "East US"
  resource_group_name = "Enter resource group name"
}

resource "azurerm_network_security_rule" "example1" {
  name                        = "Web80"
  priority                    = 1001
  direction                   = "Inbound"
  access                      = "Allow"
  protocol                    = "Tcp"
  source_port_range           = "80"
  destination_port_range      = "80"
  source_address_prefix       = "*"
  destination_address_prefix  = "*"
  resource_group_name         = "Enter Resource group name"
  network_security_group_name = azurerm_network_security_group.nsg.name
}

resource "azurerm_network_security_rule" "example2" {
  name                        = "Web8080"
  priority                    = 1000
  direction                   = "Inbound"
  access                      = "Deny"
  protocol                    = "Tcp"
  source_port_range           = "8080"
  destination_port_range      = "8080"
  source_address_prefix       = "*"
  destination_address_prefix  = "*"
  resource_group_name         = "Enter Resource group name"
  network_security_group_name = azurerm_network_security_group.nsg.name
}

  resource "azurerm_network_security_rule" "example4" {
  name                        = "SSH"
  priority                    = 1100
  direction                   = "Inbound"
  access                      = "Allow"
  protocol                    = "Tcp"
  source_port_range           = "*"
  destination_port_range      = "22"
  source_address_prefix       = "*"
  destination_address_prefix  = "*"
  resource_group_name         = "Enter Resource group name"
  network_security_group_name = azurerm_network_security_group.nsg.name
}

  resource "azurerm_network_security_rule" "example3" {
  name                        = "Web80Out"
  priority                    = 1000
  direction                   = "Outbound"
  access                      = "Deny"
  protocol                    = "Tcp"
  source_port_range           = "80"
  destination_port_range      = "80"
  source_address_prefix       = "*"
  destination_address_prefix  = "*"
