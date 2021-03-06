# Azure Managed Identities

This module is part of Cloud Adoption Framework landing zones for Azure on Terraform.

You can instantiate this directly using the following parameters:

```hcl
module "caf" {
  source  = "aztfmod/caf/azurerm"
  version = "5.4.2"
  # insert the 7 required variables here
}
```

## Example scenarios

The following examples are available:

| Scenario                                                     | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [100-msi-levels](./100-msi-levels)     | Deploys 4 levels of managed service identities. |

## Run this example

You can run this example directly using Terraform or via rover:

### With Terraform

```bash
#Login to your Azure subscription
az login

#Run the example
cd /tf/caf/examples

terraform init

terraform [plan | apply | destroy] \
  -var-file ./managed_service_identity/100-msi-levels/configuration.tfvars
```

### With rover

To test this deployment in the example landingzone, make sure the launchpad has been deployed first, then run the following command:

```bash
rover \
  -lz /tf/caf/examples \
  -var-folder  /tf/caf/examples/managed_service_identity/100-msi-levels/ \
  -level level1 \
  -a [plan | apply | destroy]
```