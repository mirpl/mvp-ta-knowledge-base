# PF-Onboarding

# Processes

Everything good and exciting about PowerFarm starts with creating the new Process 💬. 


>**💬 Definition alert!** 🔔
Process - Single test script that can work on its own and perform one task. It can be combined with other scripts to create the whole scenario of the test case.

First, select the ‘Processes’ button on the left side of the screen and click the ‘Create New Process’ button on the top right corner. 
It doesn’t sound complicated, right? 😎

Now, fill the displayed form.
Name your Process, and do it wisely, so that you and other users could find it easily later. 

> 💡 Remember, you can use all kinds of letters and signs along with spaces while entering the Process name.

Add the Process description. 

💡 Although it is an optional action, we recommend you to fill this space, too; it will make navigating on the list of all Processes easier both for you and other users. 

Select technology: just drop-down the list of technologies in which you wrote your test script and click the one you need. 

Now, select one of the script directories - also accessible on the drop-down list - and enter the path to the script you want to use in this Process.
 
💡 Remember that you can add a new repository by the Settings menu. 

Are you absolutely sure entered data is just as you like it? If so, don’t hesitate to click the ‘Create new Process’ button. 

It isn’t what you want to have on your list? Simply click the ‘Cancel’ button and come back to the form later. Only remember - there are no drafts here. 

Awesome! Your first Process has been created! 🙌

But it doesn’t mean your job is done here. 
Click the Process’s name to open it and check the essential details displayed on the screen you didn’t have access to while creating it. 


The list of commits is empty until you push commits in your repository.
Find the space ASSIGNED FOLDER IN REPOSITORY, copy the link to your repository, and go to it to execute your first commits. 

Well done! 👌

Now you can see the commits notification in Process details and continue your work.


It’s time to add Local Arguments 💬 to your Process by clicking the ‘Add Local Arguments’ button and filling the form displayed on the screen. Enter the Argument name and the Default value, and click the ‘Save’ button or dismiss this action clicking the ‘Close’ button. You can add as many Arguments as you wish and the list of all Arguments will be visible in the Process details. 

💬 Definition alert! 🔔
Local arguments - defined values with a name your test can use when executing, assign to every single script.

# Workflows

Creating the Workflow 💬  is another step in your adventure with PowerFarm. And it’s not a complicated operation either.

💬 Definition alert! 🔔
Workflow - Set of scripts that can be executed in a sequence or simultaneously without any dependencies. 


Click the ‘Create new workflow’ button on the top right corner of the screen to display the form to fill. 

For now, you only provide the Workflow’s name, an optional description, and choose a Parallel💬  or Sequential💬  checkbox. Once you click the ‘Save’ button, your new Workflow will appear on the list. 

💡 We recommend creating both Parallel and Sequential Workflows to practice the following steps.


💬 Definition alert! 🔔
Sequential - scripts are executed one after another. If one script fails then the next ones are not executed.


💬 Definition alert! 🔔
Parallel - scripts are executed at the same time without any dependencies.


Select your new Parallel workflow from the list to display the details on the screen and add a Flow to it. 
It’s easy - just click the ‘Add processes to the workflow’ button on the bottom of the page and choose as many Processes as you wish by clicking at the ‘Add’ button next to them on the displayed form. 

💡 Remember, the form will show all created Processes in the application, so make sure you have a proper amount on the Processes list to practice this step.

Once you’ve finished adding Processes to your new Workflow, confirm this action by clicking the ‘Save Process for Workflow’. If you want to dismiss it, click the ‘Close’ button and none of the chosen Processes will be added. 
In case you need to edit the Workflow, click the ‘Edit Flow’ button. 

Excellent! Give yourself pat on the back and keep on. 👊


# Jobs
You now know how to create Processes and Workflows, but to start the actual experience of Test Automation, you need to create the Job 💬.

💬 Definition alert! 🔔
Job - Execution of a Workflow.

## Create a new job

There are two ways of creating a new Job.
First, find the ‘Create Job’ button on the Workflows list, next to every Workflow.
Second, open Workflow’s details and find the ‘Create Job’ button in the top right corner of the page. 
Clicking the ‘Create Job’ button will open the form to fill in.

💡 Remember, if the button is unclickable, the Processes were not added to the Workflow yet.

💡 You can return to the added Process details page by clicking the ‘Go to Process’ button. 

Filling in the ‘Create New Job’ form consists of four steps. A separate form and graphic pointer outline each of them:

## Choose Versions of the Processes

The form of choosing the Process Version displays every Process added to the Workflow. For each of them, select branch along with commit you want to use for this Job.

💡 Remember, if there were no commits in the Process, you cannot select Branch and Commit.

Next, select the Tag and Commit hash 💬. 

💡 Notice, choosing both Tags and Commit hash is optional for every Process.

💬 Definition alert! 🔔
Commit hash - the code version used by the Process


## Choose Arguments Collections

In the second step, choose Global Arguments 💬 you want to add to this Job, and click the ‘Save and go to Arguments’ button. 

💡 Remember, collections of Global Arguments are created in the Settings menu.

💬 Definition alert! 🔔
Global Arguments - sets of values with names you can predefine globally and use when executing a set of tests (such as environment URLs or login credentials).

## Define Arguments Values

In the third step, you can edit the Local Arguments you added while creating the Processes. They will be used for this Job execution.

💡  Remember, if you set Global Arguments in the previous step, they will be overriding for the Local Arguments.

## Executing the Job

In the fourth step, choose one of two available methods of executing the Job:
Create Job immediately 💬 or Create Trigger 💬. 


💬 Definition alert! 🔔
Immediate Job - the Job executed right away after creating it.
Trigger - an instruction to execute scripts on defined date and time.

### Create Job Immediately 
That’s straight forward action - the Job will be executed right away after clicking the ‘Create Job’ button. 
The form will be shut down and you will see the window confirming creating New Job with its ID number and two buttons:
‘Go back to the Workflow/List’ - reopens the Workflow/List view (depends on which view you started creating Job with - Workflow or List); 
‘Go to the Jobs Details’ - takes you back to the Job detail view.
### Create Trigger
Selecting this option gives you more alternatives regarding the scheduling and repeating Job in defined periods of time - in other words, you create the Trigger. The Job won’t be executed right away.
Choose the Execution Date and the Execution Time.


💡  Remember, the Execution Time must be at least 5 minutes ahead.

If you don’t want the Job to repeat, select the option ‘Never’. 

💡  Remember, you cannot set the Finish date if you selected the option ‘Never’.

In case you wish to repeat the Job, choose the option ‘Daily’, ‘Weekly’, or ‘Monthly’ and set the Finish date. 

All setup? Do not hesitate then and click the ‘Create Trigger’ button 👆

The form will be shut down and you will see the window confirming creating New Job with the Trigger’s ID number, Job’s name, schedule details, and two buttons:
‘Go back to the Workflow/List’ - reopens the Workflow/List view (depends on which view you started creating Job with - Workflow or List); 
‘Go to the Trigger Details’ - takes you back to the Job detail view.

## Results

Curious about the results of your so-far work? Of course, you are 😉

Go to the Jobs list and check out what it displays.
ID - the unique Job ID, set by the system
Workflow name - the one you entered while creating the Workflow
Start date & End Date - if the Job is scheduled; Immediate Jobs will show N/A
Status - you will learn in what status is your Job at the moment
Ordered by - the name of the Job creator

If you want to see more detailed info about the Job, click on the ID of the selected one. 

The page with the Job containing Parallel Workflow or Sequential Workflow allows you to check the following details you didn’t have access to from the list page:
Process name - along with the link (Parallel Workflow) or the ‘Show Results’ button (Sequential Workflow) opening the window displaying the results of the Process execution:
- Status
- Start Date
- End Date
- Execution Time
- Output - displayed in JSON format
- Input parameters - Name & Value
- Generated files 
- Screenshots
Workflow information - ‘Type’ & ‘Created by’, along with the ‘Go to workflow’ link, moving the user to the Workflow page.
The ‘Return Job’ button - the button that lets to repeat the Job one more time.

💡 Notice the difference between the way of displaying the Parallel and Sequential Workflows.

### Statuses
Now, let’s look closely at the statuses, and what they really mean. 👀

 When the Job has been ordered, but its execution didn’t start yet 😐. In Details space, you will see the info: ‘No jobs were created for this order”, and there will be no Start and End Time provided. 

 When a new Job is created.

 When the Job is canceled by the user before it started execution.

 When at least one connected Process is pending (and others can be created).

 When one of the Processes cannot be built, or the order cannot be submitted to the queue 😟. When you go to check the results, you will see the respective info in the ‘Output’ window. 

 When a robot could not be built

  When at least one Process is currently running

 When the execution of this Job succeeded 😀. When you go to see the results, you will see the respective info in the ‘Output’ window.


You've gone so far in this exciting journey 👏. Catch some breath, and let's move on!

# Schedule
Last but not least stage of your trip through PowerFarm platform is to learn more about Schedule and Triggers 👇


The schedule list contains all Jobs for which the user created Trigger: set the precise execution time and, in some cases, also determined the Job repetitions in defined periods and its finish date. 

💡  Remember, the Triggers were created while setting up New Jobs; if you want to change them, get back to the Jobs details.

Go to the Schedule list, and check out the details it displays.
ID - the number, which, at the same time, is the link directing to the Schedule details
Workflow name - the name the creator gave for this Workflow 
Trigger details - Workflow’s execution date and hour
Next run - displayed when the Workflow hasn’t been finished yet
Finish date - displayed when the Workflow has been completed
Buttons:
Pause Trigger - available for ongoing Workflows; click it if you want to pause the Trigger for some time
Resume - available for the paused Workflows; click it if you want to resume given Workflow
Delete - available for the paused Workflows; click it if you want to delete given Workflow
Trigger Finished - that indicates the Workflow has been completed

The Schedule list contains a pretty lot of data, doesn’t it? But in case you want to see more, click at any Workflow ID and check out the Jobs statuses.


Well, that would be it for your onboarding ✅
You've done well and deserve some rest. But the journey with PowerFarm only begins, and if you'd need to find out more, check out the documentation we prepared for you or contact our Team. We’re always happy to help 🙋

