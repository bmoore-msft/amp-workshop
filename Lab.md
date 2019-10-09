# Azure Application Offer Lab

## Getting Started

- [ ] Install [Visual Studio Code](https://code.visualstudio.com/Download)

- [ ] Install the [Azure Resource Manager Tools Extension](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools)

- [ ] Clone or copy: https://github.com/bmoore-msft/amp-workshop.git - you can also grab files from the Azure QuickStarts repo, the [Marketplace Sample](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools) and the [ARM Template Toolkit](https://github.com/Azure/azure-quickstart-templates/tree/master/test/template-tests)

- [ ] Install Azure PowerShell or the Az CLI

## Deploy the Template

- [ ] Modify the template for any changes you want or you can skip this step for a quick test

- [ ] Update the parameters file to supply your own valid parameter values

- [ ] Deploy the template using PowerShell or the CLI

```Powershell
.\Deploy-AzTemplate.ps1 -ArtifactStagingDirectory .\contoso-portal\ -location westus
```

```bash
az-group-deploy.sh -a contos-portal -l westus
```

## Adding and Testing the UI (CreateUIDefinition.json)

- [ ] Sideload the CreateUIDefintion.json file in the Azure portal for testing

```PowerShell
.\SideLoad-AzCreateUIDefinition.ps1 -ArtifactsStagingDirectory .\contoso-portal
```

```bash
sideload-creatuidef.sh -a contoso-portal
```

- [ ] Test the UI in the Azure Portal, bring up the console in the browser (F12) to see the debug output

- [ ] Fix any errors and test to verify they have been fixed

- [ ] After a successful test, the parameters sent to the template deployment will be displayed in the debug console in the browser - copy those parameters and do a test deployment to verify the offer end to end.

## Adding the Attribution GUID

- [ ] Create the tracking GUID in the publishing portal

- [ ] Modify the template to add the attribution resource according to this [doc](https://docs.microsoft.com/en-us/azure/marketplace/azure-partner-customer-usage-attribution)

- [ ] Test the template with the changes

## Test the template for Best Practices using the ARM Template Toolkit (TTK)

- [ ] Use the TTK to check the template for Best Practice violations

- [ ] First import the module

```PowerShell
Import-Module .\template-tests\AzRMTester.psd1
```

- [ ] Execute the tests

```PowerShell
Test-AzureRMTemplate -TemplatePath .\contoso-portal
```

- [ ] Fix any errors reported by the tests

## Building the Package and Publishing the Offer

- [ ] Create the zip file

- [ ] Go to the [Cloud Partner Portal](https://cloudpartner.azure.com) and create a new Azure Application Offer

- [ ] Fill in the offer detals and save the offer

- [ ] Add a new SKU and upload the package

- [ ] Fill in details for the SKU, Marketplace and Support Sections of the Offer and SKU

- [ ] Save the offer and click Publish

- [ ] Get Coffee

- [ ] Fast-Forward to the next step and click "Go Live" - this will create a work item in the review queue

## Azure DevOps Code Review

- [ ] When an offer is "Rejected", which shows as a "Publish Failed" publish there will be a link to the PR with comments that need to be addressed

- [ ] As a publisher you can respond to comments to ask questions or clarifications as needed.

- [ ] To make changes or fixes, simply publish a new package through the publishing portal
