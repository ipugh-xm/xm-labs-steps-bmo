# BMO Steps

This step allows you to create a bug in [BMO](https://github.com/mozilla-bteam/bmo) (a fork of Bugzilla).


---------

<kbd>
<a href="https://support.xmatters.com/hc/en-us/community/topics">
   <img src="https://github.com/xmatters/xMatters-Labs/raw/master/media/disclaimer.png">
</a>
</kbd>

---------

# Files

* [BMOSteps.zip](BMOSteps.zip) - Workflow zip file with the step and example flow
* [bugzilla.png](/bugzilla.png) - Bugzilla logo

# How it works
This step uses the `/rest/bug` endpoint in BMO. [Here](https://bmo.readthedocs.io/en/latest/api/core/v1/bug.html#create-bug) is the documentation for it.


# Installation

## BMO Setup
This step requires an API key for BMO to work.

1. Go to your user preferences.
2. On the left side there should be a tab called **API Keys**. Click on it.
3. Generate or copy an API key from the page. This will be later used to create a constant in xMatters.


## xMatters Setup
1. Download the [BMOSteps.zip](BMOSteps.zip) file onto your local computer
2. Navigate to the Workflows tab of your xMatters instance
3. Click Import, and select the zip file you just downloaded
4. Create a constant with your BMO API key and then use in inside the `BMO - Create Bug` step.


## Usage
The **BMO - Create Bug** step is now available in your custom steps. So navigate to the appropriate canvas so you can add the step there. If you'd like to experiment with it, the **Create Bug** workflow has a canvas that can be triggered via HTTP call. 

### Inputs
| Name  | Required? | Min | Max | Help Text | Default Value | Multiline |
| ----- | ----------| --- | --- | --------- | ------------- | --------- |
| Product | Yes | 0 | 2000 | The name of the product the bug is being filed against. | | No |
| Component | Yes | 0 | 2000 | The name of a component in the product above. | | No |
| Summary | Yes | 0 | 2000 | A brief description of the bug being filed. | | No |
| Version | Yes | 0 | 2000 | A version of the product above; the version the bug was found in. | | No |
| API Key | Yes | 0 | 2000 | API Key from BMO | | No |
| Type | Yes | 0 | 2000 | Type of bug. (sometimes required) | | No |


### Outputs

| Name | Description |
| ---- | ----------  |
| ok | (true) it passed, or (false) the request failed. |
| id | id of the bug filed if it succeeded |


## Example
This is what the **Create Bug** provided flow looks like.

<kbd>
	<img src="/media/ExampleFlow.png">
</kbd>

