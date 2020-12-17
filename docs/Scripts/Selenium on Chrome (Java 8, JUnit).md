# Selenium on Chrome (Java 8, JUnit)

<!-- theme: warning -->
> 💡 **Important**: JUnit 4 is supported as a runner; JUnit 5 is used for assertions solely. 

The example used to describe the Selenium technology contains two tests, executed together in one sequential workflow ‘Add task and mark as done’:
AddItemFromHeader
MarkTaskAsDone



The following scripts were used to create this task:


### Test 1 - AddItemFromHeader

<!--
title: The following scripts were used to create this task
lineNumbers: true
-->

```java
package ai.makeitright.tests.additemfromheader;

import ai.makeitright.pages.MainTodoistPage;
import ai.makeitright.utilities.DriverConfig;
import org.json.JSONObject;
import org.junit.After;
import org.junit.Before;
import org.junit.Test;
import org.junit.jupiter.api.Assertions;

public class AddItemFromHeader extends DriverConfig {

   private String taskName;
   private String url;
   @Before

   public void before() {
       url = System.getProperty("secretParameters.url");
       taskName = System.getProperty("inputParameters.taskName");
   }

   @Test
   public void addItemFromHeader() {

       driver.get(url);
       driver.manage().window().maximize();
       MainTodoistPage mainPage = new MainTodoistPage(driver);

       mainPage.clickButtonPlus_Header();
       taskName = mainPage.setTaskName(taskName);
       mainPage.clickButtonAddTask();

       Assertions.assertTrue(mainPage.isTaskAtInbox(taskName));

   }

   @After
   public void prepareJson() {
       JSONObject obj = new JSONObject();
       obj.put("taskName",taskName);
       System.setProperty("output", obj.toString());
       driver.close();
   }
}
```



### Test 2 - MarkTaskAsDone

```javascript
package ai.makeitright.tests.marktaskasdone;

import ai.makeitright.pages.MainTodoistPage;
import ai.makeitright.utilities.DriverConfig;
import org.json.JSONObject;
import org.junit.After;
import org.junit.Before;
import org.junit.Test;
import org.junit.jupiter.api.Assertions;

public class MarkTaskAsDone extends DriverConfig {

   private String taskName;
   private String url;

   @Before
   public void before() {
       url = System.getProperty("secretParameters.url");
       taskName = System.getProperty("previousResult.taskName");
   }

   @Test
   public void markTaskAsDone() {

       driver.get(url);
       driver.manage().window().maximize();

       MainTodoistPage mainPage = new MainTodoistPage(driver);

       Assertions.assertTrue(mainPage.markTaskDone(taskName),"There is no task with name '" + taskName + "' on the Inbox list");
       Assertions.assertFalse(mainPage.isTaskAtInbox(taskName),"Task with name '" + taskName + "' is still visible on the Inbox list");
   }

   @After
   public void prepareJson() {
       JSONObject obj = new JSONObject();
       obj.put("detetedTaskName",taskName);
       System.setProperty("output", obj.toString());
       driver.close();
   }
}
```


## Script path

<!-- theme: warning -->
> 💡 **Remember** to ensure that your repository is added to the list at the Repository Addresses on the PowerFarm platform.





In the package with scripts, create a separate subpackage for every script.



Thus, it will become the path to enter while creating new tasks on the PowerFarm platform.

Choose your repository while creating a new Task, and paste the respective script path from it. 



## Script details
### @Test annotation

Creating a script, add annotation @Test 

```javascript
@Test
public void addItemFromHeader() {
```
## Parameters

There are three possible parameters you can add to your script:
1. `secretParameter` - encrypted arguments
2. `inputParameter` 
3. `previousResults` - passing arguments from the previous test

On the PowerFarm platform, there are two types of parameters, called arguments:
1. **local arguments** - can be added to and used in one script only;
2. **global arguments** - can be used in many scripts.

<!-- theme: warning -->
>💡 **Remember**, there is no differentiation between local and global arguments (parameters) in scripts.


### Test 1 - AddItemFromHeader

In this script, there are two parameters used:

1. **secret Parameters**

```javascript
url = System.getProperty("secretParameters.url");
```


the encrypted global argument (the argument that can be used in many tasks), invisible in the PowerFarm platform.



2. **input Parameters **

```javascript
taskName = System.getProperty("inputParameters.taskName");
```
the local argument (used only for this specific task).


### Test 2 - MarkTaskAsDone

In this script, there are two parameters used:

1. **secret Parameters**
```javascript
url = System.getProperty("secretParameters.url");
```

the encrypted global argument (the argument that can be used in many tasks), invisible in the PowerFarm platform.

2. **previous Result **
```javascript
taskName = System.getProperty("previousResult.taskName");
```
passing the argument from the previously executed task; it is not seen in the details of this task, but the output of the previous task.

<!-- theme: info -->
>💡 **Notice**, the parameter can be used in the script, but no results will be displayed if there was no specify what kind of argument should be executed in the tests.

## Environment variables

### Output
The output is displayed in JSON format. So, write the script according to the example:
```javascript
public void prepareJson() {
       JSONObject obj = new JSONObject();
       obj.put("detetedTaskName",taskName);
       System.setProperty("output", obj.toString());
       driver.close();
```

> **Notice**, the platform currently supports only **string** as allowable task output value.

The output of the executed tasks in the workflow (job) is displayed on the PowerFarm platform in the job’s details (job’s results). 




