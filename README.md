# Key Vault Acmebot Terraform module Fork

Original: https://github.com/shibayan/terraform-azurerm-keyvault-acmebot

I had to change it to use pre-existing logws + appinsight + storageaccount if they are specified

## Usage

```hcl
module "keyvault_acmebot" {
  source  = "https://github.com/milkfinch/terraform-azurerm-keyvault-acmebot//"

  app_base_name         = "acmebot-module"
  resource_group_name   = azurerm_resource_group.default.name
  location              = azurerm_resource_group.default.location
  mail_address          = "YOUR-EMAIL-ADDRESS"
  vault_uri             = azurerm_key_vault.default.vault_uri

  azure_dns = {
    subscription_id = data.azurerm_client_config.current.subscription_id
  }
}
```

## License

This project is licensed under the [Apache License 2.0](https://github.com/shibayan/terraform-azurerm-keyvault-acmebot/blob/master/LICENSE)
