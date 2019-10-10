# Github Steps

This step allows you to get the commit details from a given repo and user. Great for enriching notifications with relevant code commit information. 


---------

<kbd>
  <img src="https://github.com/xmatters/xMatters-Labs/raw/master/media/disclaimer.png">
</kbd>

---------

# Files

* [GitHub-small.png](/GitHub-small.png) - GitHub logo

# How it works
The step pulls the commit information using the GitHub REST API GET `/repos/{Username}/{Repository}/commits/master`.


# Installation

## GitHub Setup
None. This uses repos in GitHub.com which are public. If your GitHub requires authentication, some tweaking might be needed. 

## xMatters Setup
1. Download the GithubStep.zip file onto your local computer
2. Navigate to the Developer tab of your xMatters instance
3. Click Import, and select the zip file you just downloaded


## Usage
The *GitHub - Get last commit* step is now available in your custom steps. So navigate to the appropriate canvas so you can add the step there. If you'd like to experiment with it, the **GitHub Steps** workflow has a canvas that can be triggered via HTTP call. 

### Inputs
| Name  | Required? | Min | Max | Help Text | Default Value | Multiline |
| ----- | ----------| --- | --- | --------- | ------------- | --------- |
| Username  | Yes | 0 | 2000 | The username or organization the repository lives under | | No |
| Repository | Yes | 0 | 2000 | The name of the repository | | No |


### Outputs

| Name | Description |
| ---- | ----------  |
| URL | URL of the repository |
| SHA | The SHA hash of the commit |
| Author_Name | Full name of the author. |
| Author_Email | Email address of the author. | 
| Timestamp | Timestamp of the commit. |
| Message | Commit message |



## Example
This is an example showing the GitHub and Jenkins steps enriching the event before it is fired off to people. 

<kbd>
	<img src="/media/ExampleFlow.png">
</kbd>

