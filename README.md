# GitHub Steps

Steps that allow various interactions with GitHub


---------

<kbd>
  <img src="https://github.com/xmatters/xMatters-Labs/raw/master/media/disclaimer.png">
</kbd>

---------

# Files

* [GitHubSteps.zip](GitHubSteps.zip) - Workflow zip file with the step and example flow
* [GitHub-small.png](/GitHub-small.png) - GitHub logo

# How it works
- GitHub - Get Last Commit : queries for the last commit for a branch or tag and returns details
- GitHub - Get Commit : queries for a specific commit and returns details
- GetHub - Get Pull Request : queries for a specific pull request and returns details
- GetHub - Trigger Workflow : triggers a GitHub workflow


# Installation

## GitHub Setup
1. Create a personal access token

## xMatters Setup
### Import Steps
1. Download the [GitHubSteps.zip](GitHubSteps.zip) file onto your local computer
2. Navigate to **Workflows** of your xMatters instance
3. Click Import, and select the zip file you just downloaded

### Setting up Endpoint
1. Create and/or open the workflow you want to use the GitHub steps in
2. Go to the **Flow Designer** tab, open the **Components** menu in the top right, and select **Endpoints**
3. Add a new endpoint and enter the following information
    - Name = GitHub
    - Base URL = https://api.github.com
    - Endpoint Type = Basic
    - Username = *GitHub username*
    - Password = *GitHub personal access token*
    - Preemptive = checked


# Usage
## GitHub - Get Last Commit
The **GitHub - Get Last Commit** step can be used to query for the last commit for a branch or tag.  It will return various details.

### Inputs
| Name  | Required? | Min | Max | Help Text | Default Value | Multiline |
| ----- | ----------| --- | --- | --------- | ------------- | --------- |
| Continue On Error | No | 0 | 5 | The name of the repository | false | No |
| Repository Owner  | No | 0 | 2000 | The username or organization the repository lives under | | No |
| Repository Name | No | 0 | 2000 | The name of the repository | | No |
| Ref | No | 0 | 2000 | Branch or Tag | | No |

### Outputs

| Name | Description |
| ---- | ----------  |
| URL | URL to the commit |
| SHA | The SHA hash of the commit |
| Committer Name | Full name of the author |
| Committer Email | Email address of the author | 
| Author Name | Full name of the author |
| Author Email | Email address of the author | 
| Timestamp | Timestamp of the commit. |
| Message | Commit message |
| Slack Changes | Changes in Slack markdown format |
| HTML Changes | Changes in HTML format |
| Step Error | true or false depending on if step encountered an error |

---

## GitHub - Get Commit
The **GitHub - Get Commit** step can be used to query for a specific commit using its SHA.  It will return various details.

### Inputs
| Name  | Required? | Min | Max | Help Text | Default Value | Multiline |
| ----- | ----------| --- | --- | --------- | ------------- | --------- |
| Continue On Error | No | 0 | 5 | The name of the repository | false | No |
| Repository Owner  | No | 0 | 2000 | The username or organization the repository lives under | | No |
| Repository Name | No | 0 | 2000 | The name of the repository | | No |
| SHA | No | 0 | 2000 | The SHA hash of the commit | | No |

### Outputs

| Name | Description |
| ---- | ----------  |
| URL | URL to the commit |
| Committer Name | Full name of the author. |
| Committer Email | Email address of the author. | 
| Author Name | Full name of the author |
| Author Email | Email address of the author | 
| Timestamp | Timestamp of the commit |
| Message | Commit message |
| Slack Changes | Changes in Slack markdown format |
| HTML Changes | Changes in HTML format |
| Step Error | true or false depending on if step encountered an error |

---

## GitHub - Get Pull Request
The **GitHub - Get Pull Request** step can be used to query for a specific pull request by number.  It will return various details.

### Inputs
| Name  | Required? | Min | Max | Help Text | Default Value | Multiline |
| ----- | ----------| --- | --- | --------- | ------------- | --------- |
| Continue On Error | No | 0 | 5 | The name of the repository | false | No |
| Repository Owner  | No | 0 | 2000 | The username or organization the repository lives under | | No |
| Repository Name | No | 0 | 2000 | The name of the repository | | No |
| Pull Request Number | No | 0 | 2000 | The pull request number | | No |

### Outputs

| Name | Description |
| ---- | ----------  |
| URL | URL to the pull request |
| Requestor Name | Name of the requestor |
| Timestamp | Timestamp of the commit. |
| Title | Pull request title |
| Message | Commit message |
| Source | Pull request source |
| Target | Pull request target |
| Step Error | true or false depending on if step encountered an error |

---

## GitHub - Trigger Workflow
The **GitHub - Trigger Workflow** step can be used to start a GitHub workflow with a "workflow_dispatch" trigger.
#### :blue_book: NOTE
> The workflow must be set to trigger on "workflow_dispatch"

### Inputs
| Name  | Required? | Min | Max | Help Text | Default Value | Multiline |
| ----- | ----------| --- | --- | --------- | ------------- | --------- |
| Continue On Error | No | 0 | 5 | The name of the repository | false | No |
| Repository Owner  | No | 0 | 2000 | The username or organization the repository lives under | | No |
| Repository Name | No | 0 | 2000 | The name of the repository | | No |
| Workflow | No | 0 | 2000 | Workflow ID or file name | | No |
| Ref | No | 0 | 2000 | Branch or Tag where the workflow is located | | No |
| Workflow Inputs | No | 0 | 20000 | Comma separated list of key value pairs for the inputs of the GitHub Action workflow. ("input1":"value1","input2":"value" | | No |

### Outputs

| Name | Description |
| ---- | ----------  |
| Step Error | true or false depending on if step encountered an error |
