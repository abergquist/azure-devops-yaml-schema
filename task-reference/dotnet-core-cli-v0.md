---
title: DotNetCoreCLI@0 - .NET Core v0 task
description: Build, test and publish using dotnet core command-line (task version 0).
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# DotNetCoreCLI@0 - .NET Core v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Build, test and publish using dotnet core command-line.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# .NET Core v0
# Build, test and publish using dotnet core command-line.
- task: DotNetCoreCLI@0
  inputs:
    command: 'build' # 'build' | 'publish' | 'restore' | 'test' | 'run'. Required. Command. Default: 'build'.
    #publishWebProjects: true # boolean. Required when command = publish. Publish Web Projects. Default: true.
    #projects: # string. Optional. Use when command != publish || publishWebProjects = false. Project(s). 
    #arguments: # string. Arguments. 
    #zipAfterPublish: true # boolean. Optional. Use when command = publish. Zip Published Projects. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="command"::: -->
:::moniker range="<=azure-pipelines"

**`command`** - **Command**<br>
Type: string. Required. Allowed values: 'build', 'publish', 'restore', 'test', 'run'. Default value: 'build'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The dotnet command to run. Select `custom` to add arguments or use a command not listed here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishWebProjects"::: -->
:::moniker range="<=azure-pipelines"

**`publishWebProjects`** - **Publish Web Projects**<br>
Type: boolean. Required when command = publish. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If true, the `projects` property value is skipped and the task tries to find the web projects in the repository and run the publish command on them. Web projects are identified by presence of either a web.config file or wwwroot folder in the directory. In the absence of a web.config file or wwwroot folder, projects that use a web SDK, like Microsoft.NET.Sdk.Web, are selected.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="projects"::: -->
:::moniker range="<=azure-pipelines"

**`projects`** - **Project(s)**<br>
Type: string. Optional. Use when command != publish || publishWebProjects = false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the csproj file(s) to use. You can use wildcards (e.g. `**/*.csproj` for all .csproj files in all subfolders). For more information, see [file matching patterns reference](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Arguments to the selected command. For example, build configuration, output folder, runtime. The arguments depend on the command selected.

This input only currently accepts arguments for `build`, `publish`, `run`, `test`, `custom`. If you would like to add arguments for a command not listed, use `custom`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="zipAfterPublish"::: -->
:::moniker range="<=azure-pipelines"

**`zipAfterPublish`** - **Zip Published Projects**<br>
Type: boolean. Optional. Use when command = publish. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If true, folder created by the publish command will be zipped and deleted.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

> [!IMPORTANT]
> `DotNetCorCLI@0` is deprecated. For a newer supported version, see [DotNetCoreCLI@2](dotnet-core-cli-v2.md).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.95.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [DotNetCoreCLI@2](dotnet-core-cli-v2.md)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->