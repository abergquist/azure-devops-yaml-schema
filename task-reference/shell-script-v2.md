---
title: ShellScript@2 - Shell script v2 task
description: Run a shell script using Bash.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# ShellScript@2 - Shell script v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Run a shell script using Bash.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Run a shell script using bash.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Shell script v2
# Run a shell script using Bash.
- task: ShellScript@2
  inputs:
    scriptPath: # string. Required. Script Path. 
    #args: # string. Arguments. 
  # Advanced
    #disableAutoCwd: false # boolean. Specify Working Directory. Default: false.
    #cwd: # string. Optional. Use when disableAutoCwd = true. Working Directory. 
    #failOnStandardError: false # boolean. Fail on Standard Error. Default: false.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
# Shell Script v2
# Run a shell script using bash.
- task: ShellScript@2
  inputs:
    scriptPath: # string. Required. Script Path. 
    #args: # string. Arguments. 
  # Advanced
    #disableAutoCwd: false # boolean. Specify Working Directory. Default: false.
    #cwd: # string. Optional. Use when disableAutoCwd = true. Working Directory. 
    #failOnStandardError: false # boolean. Fail on Standard Error. Default: false.
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

<!-- :::item name="scriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`scriptPath`** - **Script Path**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from repo root of the shell script file to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="args"::: -->
:::moniker range="<=azure-pipelines"

**`args`** - **Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Arguments passed to the shell script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="disableAutoCwd"::: -->
:::moniker range="<=azure-pipelines"

**`disableAutoCwd`** - **Specify Working Directory**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The default behavior is to set the working directory to the script location. This enables you to optionally specify a different working directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cwd"::: -->
:::moniker range="<=azure-pipelines"

**`cwd`** - **Working Directory**<br>
Type: string. Optional. Use when disableAutoCwd = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Current working directory where the script is run.  Empty is the root of the repo (build) or artifacts (release), which is $(System.DefaultWorkingDirectory).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStandardError"::: -->
:::moniker range="<=azure-pipelines"

**`failOnStandardError`** - **Fail on Standard Error**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, this task will fail if any errors are written to the StandardError stream.
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

### Where can I learn about Bash scripts?

* [Beginners/BashScripting](https://help.ubuntu.com/community/Beginners/BashScripting) to get started.
* [Awesome Bash](https://github.com/alebcay/awesome-shell#awesome-bash) to go deeper.

### How do I set a variable so that it can be read by subsequent scripts and tasks?

To learn more about defining build variables in a script, see [Define and modify your build variables in a script](/azure/devops/pipelines/process/variables#set-a-multi-job-output-variable).

To learn more about defining release variables in a script, see [Define and modify your release variables in a script](/azure/devops/pipelines/release/variables#use-custom-variables)
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

Create `test.sh` at the root of your repo.
We recommend creating this file from a Linux environment (such as a real Linux machine or Windows Subsystem for Linux) so that line endings are correct.
Also, don't forget to `chmod +x test.sh` before you commit it.

```sh
#!/bin/bash
echo "Hello World"
echo "AGENT_WORKFOLDER is $AGENT_WORKFOLDER"
echo "AGENT_WORKFOLDER contents:"
ls -1 $AGENT_WORKFOLDER
echo "AGENT_BUILDDIRECTORY is $AGENT_BUILDDIRECTORY"
echo "AGENT_BUILDDIRECTORY contents:"
ls -1 $AGENT_BUILDDIRECTORY
echo "SYSTEM_HOSTTYPE is $SYSTEM_HOSTTYPE"
echo "Over and out."
```

Add the following task to your pipeline to run the previous script.

```yml
- task: ShellScript@2
  inputs:
    scriptPath: 'test.sh'
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: sh |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->