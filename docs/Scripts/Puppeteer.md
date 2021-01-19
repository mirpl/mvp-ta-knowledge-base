# Puppeteer

The example used to describe the Puppeteer technology contains one test Puppeteer screenshot sample (for new commit).



The following script was used to create this task:

```java
{  
module.exports = async function browser, {inputParameters, previousResult}) {
   const page = await browser.newPage();
   await page.goto(inputParameters.testTargetUrl);
   // console.log(await page.content());
   await page.screenshot({path: process.env.SCREENSHOTS_PATH + '/' + 'screenshot.png'});
   await page.screenshot({path: process.env.SHARED_ORDER_PATH + '/' + 'screenshot.png'});
   return {created: true, taskTitle: inputParameters.taskTitle};
}
```
<!-- theme: warning -->
>💡 **Important**: start every script as in the example: `module.exports = async function`

## Script path

<!-- theme: warning -->
>💡 **Remember** to ensure that your repository is added to the list at the Repository Addresses on the PowerFarm platform.



Choose your repository while creating a new Task, and paste the respective script path from it. 



You can copy the file path in the GitHub repository by clicking the ‘Copy path’ button.


If your script is in the GitLab repository, you can copy the file path by using the icon  .



Once the Task has been created, you can copy the repository path from the Task’s details.



## Script details

### Parameters
There are three possible parameters you can add to your script:
1. `secretParameter` - encrypted arguments
2. `inputParameter` 
3. `previousResults` - passing arguments from the previous test

On the PowerFarm platform, there are two types of parameters, called arguments:
1. local arguments - can be added to and used in one script only;
2. global arguments - can be used in many scripts.

<!-- theme: warning -->
> 💡 **Remember**, there is no differentiation between local and global arguments (parameters) in scripts. 

In this script, there are two parameters used:

1. input Parameters
```java
await page.goto(inputParameters.testTargetUrl);
```
the local argument (used only for this specific task).



2. previous Result 
```java
module.exports = async function browser, {inputParameters, previousResult}) {
```
passing the argument from the previously executed task; it is not seen in the details of this task, but the output of the previous task.

> 💡 **Notice**, the parameter can be used in the script, but no results will be displayed if there was no specify what kind of argument should be executed in the tests.

## Environment variables
In the example, as the environment variables are screenshots. 
```java
await page.screenshot({path: process.env.SCREENSHOTS_PATH + '/' + 'screenshot.png'});
   await page.screenshot({path: process.env.SHARED_ORDER_PATH + '/' + 'screenshot.png'});
```

The screenshots are displayed and can be downloaded in the Job results window.

<!-- theme: warning -->
> 💡 **Remember**, don't make variables for those as static as they are set with values during the first compilation, so they will not activate when they are called again. Thus, new paths for each job will be wrong for these subsequent robot calls - there is a risk, for example, that the job results will not include screenshots attachments.

## Output
The output is displayed in JSON format. Write the script according to the example:
```java
return {created: true, taskTitle: inputParameters.taskTitle};
```
> **Notice**, the platform currently supports only **string** as allowable task output value.

The output of the executed tasks in the workflow (job) is displayed on the PowerFarm platform in the job’s details (job’s results). 
