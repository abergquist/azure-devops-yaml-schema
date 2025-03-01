---
title: AzureAppServiceSettings@1 - Azure App Service Settings v1 task
description: Update/Add App settings an Azure Web App for Linux or Windows.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2020"
---

# AzureAppServiceSettings@1 - Azure App Service Settings v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Update/Add App settings an Azure Web App for Linux or Windows.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Azure App Service Settings v1
# Update/Add App settings an Azure Web App for Linux or Windows.
- task: AzureAppServiceSettings@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    appName: # string. Required. App Service name. 
    resourceGroupName: # string. Required. Resource group. 
    #slotName: 'production' # string. Slot. Default: 'production'.
  # Application and Configuration Settings
    #appSettings: # string. App settings. 
    #generalSettings: # string. General settings. 
    #connectionStrings: # string. Connection Strings.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2020"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `ConnectedServiceName`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`appName`** - **App Service name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter or Select the name of an existing Azure App Service.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`resourceGroupName`** - **Resource group**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter or Select the Azure Resource Group that contains the Azure App Service specified above.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="slotName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`slotName`** - **Slot**<br>
Type: string. Default value: 'production'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter or Select an existing Slot. If no slot is selected, changes will be made to production.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSettings"::: -->
:::moniker range=">=azure-pipelines-2020"

**`appSettings`** - **App settings**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Add/Update App Service App Settings using the json syntax as follows:<br/> [<br/>&nbsp;&nbsp; {<br/>&nbsp;&nbsp;&nbsp;&nbsp;"name": "key1", <br/>&nbsp;&nbsp;&nbsp;&nbsp;"value": "valueabcd",<br/>&nbsp;&nbsp;&nbsp;&nbsp;"slotSetting": false <br/> &nbsp;&nbsp; },<br/>&nbsp;&nbsp; {<br/>&nbsp;&nbsp;&nbsp;&nbsp;"name": "key2", <br/>&nbsp;&nbsp;&nbsp;&nbsp;"value": "valueefgh",<br/>&nbsp;&nbsp;&nbsp;&nbsp;"slotSetting": true <br/> &nbsp;&nbsp; }<br/>].
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="generalSettings"::: -->
:::moniker range=">=azure-pipelines-2020"

**`generalSettings`** - **General settings**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Add/Update App Service General Settings using the json syntax as follows:<br/> [<br/>&nbsp;&nbsp; {<br/>&nbsp;&nbsp;&nbsp;&nbsp;"alwaysOn": true, <br/>&nbsp;&nbsp;&nbsp;&nbsp;"webSocketsEnabled": false<br/> &nbsp;&nbsp; }<br/>].
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="connectionStrings"::: -->
:::moniker range=">=azure-pipelines-2020"

**`connectionStrings`** - **Connection Strings**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Add/Update App Service Connection strings using the json syntax as follows:<br/> [<br/>&nbsp;&nbsp; {<br/>&nbsp;&nbsp;&nbsp;&nbsp;"name": "key1", <br/>&nbsp;&nbsp;&nbsp;&nbsp;"value": "valueabcd",<br/>&nbsp;&nbsp;&nbsp;&nbsp;"type": "MySql", <br/> &nbsp;&nbsp;&nbsp;&nbsp;"slotSetting": false <br/> &nbsp;&nbsp; },<br/>&nbsp;&nbsp; {<br/>&nbsp;&nbsp;&nbsp;&nbsp;"name": "key2", <br/>&nbsp;&nbsp;&nbsp;&nbsp;"value": "valueefgh",<br/>&nbsp;&nbsp;&nbsp;&nbsp;"type": "Custom", <br/> &nbsp;&nbsp;&nbsp;&nbsp;"slotSetting": true <br/> &nbsp;&nbsp; }<br/>].
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.104.1 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->