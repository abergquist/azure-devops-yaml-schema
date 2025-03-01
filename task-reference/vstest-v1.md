---
title: VSTest@1 - Visual Studio Test v1 task
description: Run tests with Visual Studio test runner.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# VSTest@1 - Visual Studio Test v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Run tests with Visual Studio test runner.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Visual Studio Test v1
# Run tests with Visual Studio test runner.
- task: VSTest@1
  inputs:
  # Execution Options
    testAssembly: '**\*test*.dll;-:**\obj\**' # string. Required. Test Assembly. Default: '**\*test*.dll;-:**\obj\**'.
    #testFiltercriteria: # string. Test Filter criteria. 
    #runSettingsFile: # string. Run Settings File. 
    #overrideTestrunParameters: # string. Override TestRun Parameters. 
    #codeCoverageEnabled: False # boolean. Code Coverage Enabled. Default: False.
    #runInParallel: false # boolean. Run In Parallel. Default: false.
  # Advanced Execution Options
    #vstestLocationMethod: 'version' # 'version' | 'location'. VSTest. Default: 'version'.
    #vsTestVersion: '14.0' # 'latest' | '14.0' | '12.0'. Optional. Use when vstestLocationMethod = version. VSTest version. Default: '14.0'.
    #vstestLocation: # string. Optional. Use when vstestLocationMethod = location. Path to vstest.console.exe. 
    #pathtoCustomTestAdapters: # string. Path to Custom Test Adapters. 
    #otherConsoleOptions: # string. Other console options. 
  # Reporting Options
    #testRunTitle: # string. Test Run Title. 
    #platform: # string. Platform. 
    #configuration: # string. Configuration. 
    #publishRunAttachments: true # boolean. Upload Test Attachments. Default: true.
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

<!-- :::item name="testAssembly"::: -->
:::moniker range="<=azure-pipelines"

**`testAssembly`** - **Test Assembly**<br>
Type: string. Required. Default value: '**\*test*.dll;-:**\obj\**'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Test binaries to run tests on.  Wildcards can be used.  For example, `**\*test*.dll;-:**\obj\**` for all dlls with test in name while excluding files in any sub-directory named obj.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testFiltercriteria"::: -->
:::moniker range="<=azure-pipelines"

**`testFiltercriteria`** - **Test Filter criteria**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional criteria to filter tests from Test assemblies. For example: `Priority=1|Name=MyTestMethod`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runSettingsFile"::: -->
:::moniker range="<=azure-pipelines"

**`runSettingsFile`** - **Run Settings File**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to runsettings file to use with the tests. Use `$(Build.SourcesDirectory)` to access the Project folder.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideTestrunParameters"::: -->
:::moniker range="<=azure-pipelines"

**`overrideTestrunParameters`** - **Override TestRun Parameters**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Override parameters defined in the TestRunParameters section of runsettings file. For example: `AppURL=$(DeployURL);Port=8080`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageEnabled"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageEnabled`** - **Code Coverage Enabled**<br>
Type: boolean. Default value: False.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Collect code coverage information from the Test run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runInParallel"::: -->
:::moniker range="<=azure-pipelines"

**`runInParallel`** - **Run In Parallel**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enable parallel execution of your tests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstestLocationMethod"::: -->
:::moniker range="<=azure-pipelines"

**`vstestLocationMethod`** - **VSTest**<br>
Type: string. Allowed values: 'version', 'location'. Default value: 'version'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vsTestVersion"::: -->
:::moniker range="<=azure-pipelines"

**`vsTestVersion`** - **VSTest version**<br>
Type: string. Optional. Use when vstestLocationMethod = version. Allowed values: 'latest', '14.0', '12.0'. Default value: '14.0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of VSTest to use.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstestLocation"::: -->
:::moniker range="<=azure-pipelines"

**`vstestLocation`** - **Path to vstest.console.exe**<br>
Type: string. Optional. Use when vstestLocationMethod = location.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the path to VSTest.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pathtoCustomTestAdapters"::: -->
:::moniker range="<=azure-pipelines"

**`pathtoCustomTestAdapters`** - **Path to Custom Test Adapters**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Directory path to custom test adapters. Nuget restored adapters are automatically searched for.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="otherConsoleOptions"::: -->
:::moniker range="<=azure-pipelines"

**`otherConsoleOptions`** - **Other console options**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Other Console options that can be passed to vstest.console.exe. Click on the help link below for more details.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range="<=azure-pipelines"

**`testRunTitle`** - **Test Run Title**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the Test Run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="platform"::: -->
:::moniker range="<=azure-pipelines"

**`platform`** - **Platform**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Platform against which the tests should be reported. If you have defined a variable for platform in your build task, use that here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Configuration against which the tests should be reported. If you have defined a variable for configuration in your build task, use that here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishRunAttachments"::: -->
:::moniker range="<=azure-pipelines"

**`publishRunAttachments`** - **Upload Test Attachments**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Opt in/out of publishing test run level attachments.
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
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: vstest |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.89.0 or greater |
| Task category | Test |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->