# Job-Details

Curious about the results of your so-far work? Of course, you are 😉

Go to the Jobs list and check out what it displays.
- ID - the unique Job ID, set by the system
- Workflow name - the one you entered while creating the Test Plan
- Start date & End Date - if the Job is scheduled; Immediate Jobs will show N/A
- Status - you will learn in what status is your Job at the moment
- Ordered by - the name of the Job creator

If you want to see more detailed info about the Job, click on the ID of the selected one. 

The page with the Job containing Parallel Test Plan or Sequential Test Plan allows you to check the following details you didn’t have access to from the list page:
- Test name - along with the link (Parallel Test Plan) or the ‘Show Results’ button (Sequential Test Plan) opening the window displaying the results of the Test execution:
- Status
- Start Date
- End Date
- Execution Time
- Output - displayed in JSON format
- Input parameters - Name & Value
- Generated files 
- Screenshots
- Test Plan information - ‘Type’ & ‘Created by’, along with the ‘Go to Test Plan' link, moving the user to the Test Plan page.
- The ‘Return Job’ button - 
- Go to Trigger

<!-- theme: info -->
>💡 **Notice** the difference between the way of displaying the Parallel and Sequential Test Plan.

### Statuses
Now, let’s look closely at the statuses, and what they really mean. 👀


 When the Job has been ordered, but its execution hasn't started yet ??. In Details space, you will see the info: ‘No jobs were created for this order”, and there will be no Start and End Time provided. 

 When a new Job is created.

 When the Job is canceled by the user before it starts execution.

 When at least one connected Test is pending (and others can be created).

 When one of the Tests cannot be built, or the order cannot be submitted to the queue 😟. When you go to check the results, you will see the respective info in the ‘Output’ window. 

 When a robot could not be built.

  When at least one Test is currently running

 When the execution of this Job succeeded 😀. When you go to see the results, you will see the respective info in the ‘Output’ window.


You've gone so far in this exciting journey 👏. Catch some breath, and let's move on!