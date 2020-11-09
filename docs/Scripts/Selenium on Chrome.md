# Selenium-on-Chrome

# Selenium on Chrome (C#)

The example used to describe the C# technology contains one test KW_test19.

The following script was used to create this task:



```javascript
using Newtonsoft.Json;
using Newtonsoft.Json.Converters;
using Newtonsoft.Json.Linq;
using NUnit.Framework;
using OpenQA.Selenium;
using System;
using System.Dynamic;

namespace example_client
{
   namespace Google
   {
       [TestFixture]
       public class Tests
       {
           readonly Browser browser = new Browser();
           private IWebDriver driver;

           [SetUp]
           public void SetUp()
           {
               browser.Initialize();
           }

           [TearDown]
           public void TearDown()
           {
               browser.Close();
           }

           [Test]
           public void GoogleTest()
           {
               browser.Goto("https://google.com");

               driver = browser.Driver;
              
               Screenshot image = ((ITakesScreenshot) driver).GetScreenshot();
               image.SaveAsFile($"{Environment.GetEnvironmentVariable
("SCREENSHOTS_PATH")}/screenshot_1.png");
              
               JObject json = new JObject(
                   new JProperty("timestamp", "now"));
               string jsonFilePath = $"{Environment.GetEnvironmentVariable("ARTIFACTS_PATH")}/google_test_1.json";
               System.IO.File.WriteAllText(@"" + jsonFilePath, json.ToString());

               string title = driver.Title;

               Assert.AreEqual(title, "Google");
           }

           [Test]
           public void AnyPageTest()
           {
               string inputParameters = Environment.GetEnvironmentVariable("inputParameters");

               Console.WriteLine(inputParameters);

               
               dynamic parsedInputParameters = JObject.Parse(inputParameters);

               Console.WriteLine(parsedInputParameters);
               Console.WriteLine(parsedInputParameters["testTargetURL"]);
               Console.WriteLine(parsedInputParameters["expectedTitle"]);

               string targetUrl = Convert.ToString(parsedInputParameters["testTargetURL"]);
               string title = Convert.ToString(parsedInputParameters["expectedTitle"]);
              
               string previousResult = Convert.ToString(parsedInputParameters["previousResult"]);
               if (!string.IsNullOrWhiteSpace(previousResult))
               {
                   Console.WriteLine(parsedInputParameters
["previousResult"]);
                   var converter = new ExpandoObjectConverter();
                   try
                   {
                       dynamic previous = JsonConvert.DeserializeObject<ExpandoObject>(previousResult, converter);
                       targetUrl = Convert.ToString(previous.targetUrl);
                       title = Convert.ToString(previous.title);
                   }
                   catch (JsonReaderException e)
                   {
                       Console.WriteLine(e.Message);
                   }
               }
          
               browser.Goto(targetUrl);
              
               driver = browser.Driver;
               

               Screenshot image = ((ITakesScreenshot) driver).GetScreenshot();
               image.SaveAsFile($"{Environment.GetEnvironmentVariable
("SCREENSHOTS_PATH")}/screenshot_2.png");
              
               JObject json = new JObject(
                   new JProperty("timestamp", "now"));
               string jsonFilePath = $"{Environment.GetEnvironmentVariable("ARTIFACTS_PATH")}/any_page_test_2.json";
               System.IO.File.WriteAllText(@"" + jsonFilePath, json.ToString());

               string outputTitle = driver.Title;
               string outputTargetURL = driver.Url;
               
               Assert.AreEqual(title, title);
              
               Environment.SetEnvironmentVariable("output", $"{{'targetURL':'{outputTargetURL}','title':'{outputTitle}'}}");
           }
       }
   }
}
```

## Script path

<!-- theme: warning -->
>💡 Remember to ensure that your repository is added to the list at the Repository Addresses on the PowerFarm platform.



Choose your repository while creating a new Task, and paste the respective script path from it. 



Once the Task has been created, you can copy the repository path from the Task’s details.


You can copy the file path in the GitHub repository by clicking the ‘Copy path’ button.



## Script details

### Class and Methods
The presented example shows how the class and its methods can be determined in the script.
```javascript
       public class Tests
       {
           readonly Browser browser = new Browser();
           private IWebDriver driver;

           [SetUp]
           public void SetUp()
           {
               browser.Initialize();
           }

           [TearDown]
           public void TearDown()
           {
               browser.Close();
           }

           [Test]
           public void GoogleTest()
           {
               browser.Goto("https://google.com");

               driver = browser.Driver;

```
#### [SetUp]
In the given example, the [SetUp] method defines initializing the browser before executing the test. 
```javascript
           [SetUp]
           public void SetUp()
           {
               browser.Initialize();
           }
```           
#### [TearDown]
In the given example, the [TearDown] method defines closing the browser after executing the test.
```javascript
           [TearDown]
           public void TearDown()
           {
               browser.Close();
           }
```

#### [Test]
The [Test] method contains details (artifacts, parameters) of how the tests will be performed.
In the given example, there are two [Test] methods used:
```javascript
           [Test]
           public void AnyPageTest()
           {
```
and
```javascript
           [Test]
           public void AnyPageTest()
           {
```


## Environment variables
Both artifacts and parameters are taken from the environment variables. 
### Artifacts (Screenshots)
Set the command to take the screenshots as in the example below.
```javascript
            Screenshot image = ((ITakesScreenshot) driver).GetScreenshot();
```

Give a catalog name from which the screenshot will be taken and its name under which it will be displayed.
```javascript
image.SaveAsFile($"{Environment.GetEnvironmentVariable
("SCREENSHOTS_PATH")}/screenshot_1.png");
```

The screenshots are displayed and can be downloaded in the Job results window.

### Parameters

There are three possible parameters you can add to your script:
1. `secretParameter` - encrypted arguments
2. `inputParameter` 
3. `previousResults` - passing arguments from the previous test

On the PowerFarm platform, there are two types of parameters, called arguments:
1. **local arguments** - can be added to and used in one script only;
2. **global arguments** - can be used in many scripts.

<!-- theme: warning -->
> 💡 **Remember**, there is no differentiation between local and global arguments (parameters) in scripts. 


In this script - the second [Test] method - there are two parameters used:

1. **input Parameters**
```javascript
              string inputParameters = Environment.GetEnvironmentVariable("inputParameters");
```
the local argument (used only for this specific task).

The script determines two input parameters: 
```javascript
               string targetUrl = Convert.ToString(parsedInputParameters["testTargetURL"]);
               string title = Convert.ToString(parsedInputParameters["expectedTitle"]);
```

The user enters desired parameters (local arguments) in the PowerFarm platform after creating or during editing the task. They can be changed while creating a new job that contains the task.





The input parameters are displayed and can be downloaded in the Job results window.


2. previous Result 
```javascript
             string previousResult = Convert.ToString(parsedInputParameters["previousResult"]);
```
passing the argument from the previously executed task; it is not seen in the details of this task, but the output of the previous task.

>💡 **Notice**, the parameter can be used in the script, but no results will be displayed if there was no specify what kind of argument should be executed in the tests.



### Output
The output is set as a JASON Object.
```javascript
               JObject json = new JObject(
                   new JProperty("timestamp", "now"));
               string jsonFilePath = $"{Environment.GetEnvironmentVariable("ARTIFACTS_PATH")}/any_page_test_2.json";
               System.IO.File.WriteAllText(@"" + jsonFilePath, json.ToString());

               string outputTitle = driver.Title;
               string outputTargetURL = driver.Url;
               
               Assert.AreEqual(title, title);
              
               Environment.SetEnvironmentVariable("output", $"{{'targetURL':'{outputTargetURL}','title':'{outputTitle}'}}");
```               


It is displayed on the PowerFarm platform in the job results window.
