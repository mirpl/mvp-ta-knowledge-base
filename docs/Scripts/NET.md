# .NET

The following script was used to describe the C# technology:

```c
using Newtonsoft.Json;
using Newtonsoft.Json.Linq;
using OpenQA.Selenium;
using OpenQA.Selenium.Chrome;
using System;
namespace example_client
{
    class Program
    {
        static void Main(string[] args)
        {
            // setting chromedriver and chrome
            ChromeOptions chromeOptions = new ChromeOptions();
            chromeOptions.AddArgument("--no-sandbox");
            chromeOptions.AddArgument("--disable-gpu");
            chromeOptions.AddArgument("--headless");
            chromeOptions.AddArgument("--single-process");
            chromeOptions.AddArgument("--allow-file-access-from-files");
            chromeOptions.AddArgument("--disable-web-security");
            chromeOptions.AddArgument("--disable-extensions");
            chromeOptions.AddArgument("--ignore-certificate-errors");
            chromeOptions.AddArgument("--disable-ntp-most-likely-favicons-from-server");
            chromeOptions.AddArgument("--disable-ntp-popular-sites");
            chromeOptions.AddArgument("--disable-infobars");
            chromeOptions.AddArgument("--disable-dev-shm-usage");
            IWebDriver driver = new ChromeDriver(chromeOptions);
            // accessing input parameters, secret parameters and previous result
            string inputParameters = Environment.GetEnvironmentVariable("inputParameters");
            Console.WriteLine(inputParameters);
            string secretParameters = Environment.GetEnvironmentVariable("secretParameters");
            Console.WriteLine(secretParameters);
            string previousResult = Environment.GetEnvironmentVariable("previousResult");
            Console.WriteLine(previousResult);
            dynamic parsedInputParameters = JObject.Parse(inputParameters);
            driver.Url = parsedInputParameters["url"];
            // creating task output
            string output = $@"{{""result"": {{""title"":""{driver.Title}""}}}}";
            Environment.SetEnvironmentVariable("output", output);
        }
    }
}
```
## Script path

<!-- theme: warning -->
>💡 **Remember** to ensure that your repository is added to the list at the Repository Addresses on the PowerFarm platform.

Choose your repository while creating a new Test, and paste the respective script path from it. 

Once the Test has been created, you can copy the repository path from the Test's details.

You can copy the file path in your repository by clicking the ‘Copy path’ button.


## Script details

### Chromedriver setup

To set the details for your Chromedriver, use the following commands:

```c
// setting chromedriver and chrome
            ChromeOptions chromeOptions = new ChromeOptions();
            chromeOptions.AddArgument("--no-sandbox");
            chromeOptions.AddArgument("--disable-gpu");
            chromeOptions.AddArgument("--headless");
            chromeOptions.AddArgument("--single-process");
            chromeOptions.AddArgument("--allow-file-access-from-files");
            chromeOptions.AddArgument("--disable-web-security");
            chromeOptions.AddArgument("--disable-extensions");
            chromeOptions.AddArgument("--ignore-certificate-errors");
            chromeOptions.AddArgument("--disable-ntp-most-likely-favicons-from-server");
            chromeOptions.AddArgument("--disable-ntp-popular-sites");
            chromeOptions.AddArgument("--disable-infobars");
            chromeOptions.AddArgument("--disable-dev-shm-usage");

            IWebDriver driver = new ChromeDriver(chromeOptions);
```
## Environment variables
Both artifacts and parameters are taken from the environment variables. 

The screenshots - if taken - are displayed and can be downloaded in the Job results window.

### Parameters

There are three possible parameters you can add to your script:
1. `secretParameter` - encrypted arguments
2. `inputParameter` 
3. `previousResults` - passing arguments from the previous test

> **Notice** - at the moment, the `previousResults` are not used as there are only parallel tests executed.

On the PowerFarm platform, there are two types of parameters, called arguments:
1. **local arguments** - can be added to and used in one script only;
2. **global arguments** - can be used in many scripts.

<!-- theme: warning -->
> 💡 **Remember**, there is no differentiation between local and global arguments (parameters) in scripts. 




1. **input Parameters - URL**

Enter the input parameters as presented in the example:
```c
            //accessing input parameters
            string inputParameters = Environment.GetEnvironmentVariable("inputParameters");
            Console.WriteLine(inputParameters);
```

To parse JSON file from the string, 
enter:

```c
dynamic parsedInputParameters = JObject.Parse(inputParameters);
```
Next, to call its key `["url"]`, enter:

```c
            driver.Url = parsedInputParameters["url"];
```

> **Notice** - the example `inputParameters` as a string may look like this: {"url":"https://google.pl"}

### Output
To create the task output - in this case, the site title - enter:

```c
// creating task output
            string output = $@"{{""result"": {{""title"":""{driver.Title}""}}}}";
            Environment.SetEnvironmentVariable("output", output);
```            


> **Notice**, the platform currently supports only **string** as allowable task output value.

It is displayed on the PowerFarm platform in the job results window.
