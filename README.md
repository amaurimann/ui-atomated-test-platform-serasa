# cloud-web-automation-test

## Getting Started
This code was developed to demonstrate how to run web automation tests in thousands of combinations devices running at cloud.\
These tests are executed at real devices on browserStack cloud.

## Project structure

The project structure could be viewed bellow.

```
.
└── src
   └── main
       └── java
           ├── core
           │   └── BasePage.java
           │   └── BaseTest.java
           │   └── Constants.java
           │   └── BrowserFactory.java
           │   └── Constants.java
           ├── page
           │   └── AccountSitePage.java
           │   └── HirePlanPage.java
           │   └── LoginPage.java
               └── NavigationPage.java
           │── business(rules)
           │   └── LoginRules.java
           │── util
           │   └── DataGenerator.java
           │   └── ExtentManager.java
           │   └── ExtentTestManager.java
           │   └── MessagesAndLogs.java
           │   └── TestListener.java
└── src
   └── test
       └── java
           ├── test
           │   └── AccountTest.java
           │   └── HirePlanTest.java
           │   └── LoginTest.java
           │   └── NavigationTest.java
└── suites
   └── account
       └── account.chrome.tst.tst.xml
   └── hirePlans
       └── hirePlans.chrome.tst.tst.xml
   └── navigation
       └── navigation.chrome.tst.tst.xml
└── screenshots
       └── Failures
       └── Success
└── TestReport
       └── Test-Automation-Report.html
└── pom.xml
```

### core

**BasePage** is the DSL of project, all the main methods are here and used by anothers classes.

**BaseTest** it is this class that receives the device parameters for the creation of the selenium driver.

**BrowserFactory** is the heart of the project, where the Driver Selenium for the defined system is instantiated.\
The other classes extend the base page and the test page, which in turn extend the DriverFactory, giving access to the entire project by the driver instantiated here.

**Constants** class where are the browserStack credentials.

### page

**AccountSitePage** class where business rules and flows are defined.

**HirePlanPage** class where home page methods are mapped and business rules and flows are defined.

**LoginPage** class where home page methods are mapped and business rules and flows are defined.

**NavigationPage** class where home page methods are mapped and business rules and flows are defined.

### business rules

**LoginRules** class where business rules and flows for login are defined.

### util

**ExtentManager -**
**ExtentTestManager -**
**TestListener**

classes that implement the listeners and reports used in the project.

### test

**AccountTest** class that contains test methods for creation account and login.
**To see the report of this test in Browser Stack access this piblic link:**
https://automate.browserstack.com/dashboard/v2/public-build/enpOY3BONk15L3Y0RlhkL0h1bUZybnI3MTczSm5kdWNOazFiTHFMUHU4UXhHV1FQQmpoVkZVOGtoby9wVlMxcTJSTGZXWmg4aks3cGZmODkrNmZoNXc9PS0tQk4xTEVCaWRrNDJwNjB0VHFXSHZtUT09--6486ef8a89f3c40da180e6bbf4eab9b60b2dc89e

**HirePlanTest** class that contains hire plans(Serasa Premium) test methods.
**To see the report of this test in Browser Stack access this piblic link:**
https://automate.browserstack.com/dashboard/v2/public-build/bE5EQklDQW1KQnJFSEprRHR2bEZwMlJyYUdvV0VJZXh0MEJJL0pmZ2pJeDVzZ1UzOVZkVEZuOE5iejNyMDdNclpidE1MRDcyL1JzWU5JV09EaHBRVVE9PS0tdHp5VitrUEc3aGpZeHQ1NnIrcGNsZz09--4cd77d4ee324756ba396f01da776cc4312e5c69d

**NavigationTest** class that contains navigation in platform(Site Serasa) test methods.
**To see the report of this test in Browser Stack access this piblic link:**
https://automate.browserstack.com/dashboard/v2/public-build/dW5CM2RSZVZIdzl1QzJUeDZaY3ZScmE4WlFFNnpvbU5sWDVSeWFibUpOUTdXQkZLZDlRM1ZDVmhiK0pSOVNTNGhNOGlkMm9xZEZ1bDVOV3A0ek12NHc9PS0tK2JUMlRtbXhydUg0YzJTRTE0bE8zUT09--4d4c8e5807cebbec536608d02c220677a05a17b1

### suite

**account.chrome.tst.test.xml** file where parameters for running account login and account creation tests are entered.

**hirePlans.chrome.tst.test.xml** file where parameters for running hire plans tests are entered.

**navigation.chrome.tst.test.xml** file where parameters for running navigation in platform tests are entered.


### Screenshots

**Failures** folder containing screenshots of failed tests.

**Success** folder containing screenshots of success tests.

#### TestReport

**Test-Automation-Report.html** file containing the test execution report.

### pom.xml

dependency manager

### Design Pattern

The below design patterns are used at this project

```
DSL
```

```
Factory
```

```
Singleton
```

```
Strategy
```

```
page object model
```

## Running the tests

### NOTICE 1:
#### The tests will be running at BrowserStack data centers!
### NOTICE 2:
#### The account used is TRIAL and has a usage limit!

To run the suite test, you could execute manually the files located at folder `src/test/resources/suite`.\
You can also run by command line through maven commands.

## Test parameters

Tests can be performed on various operating systems and versions.\
To modify the parameters follow the instructions below.

1. The OS to test on
    - [available operating systems](https://www.browserstack.com/list-of-browsers-and-platforms/automate)
        - example: `<parameter name="os" value="Windows" />`

2. Version of the OS to test on
    - [available operating systems versions](https://www.browserstack.com/list-of-browsers-and-platforms/automate)
        - example: `<parameter name="os_version" value="10" />`

3. Browser you want to test on
    - [available browsers](https://www.browserstack.com/list-of-browsers-and-platforms/automate)
        - example: `<parameter name="browser" value="Chrome" />`

4. Browser version you want to test on
    - [available browsers versions](https://www.browserstack.com/list-of-browsers-and-platforms/automate)
        - example: `<parameter name="browser_version" value="84" />`

5. Set the resolution of your VM before beginning your test
    - [supported resolutions](https://www.browserstack.com/docs/automate/selenium/change-screen-resolution)
        - ex: `<parameter name="resolution" value="1280x800" />`

### Maven commands

```
open the terminal.
```

```
navigate to the pom.xml file folder.
```

```
run the command: mvn clean test.
```

```
to run a specific suite in a specific environment

mvn test -Denv=tst -Dsurefire.suiteXmlFiles=suites/dummies/dummies.chrome.smoke.test.xml
```

```
to run all suite test at specific environment

mvn test -Denv=tst
```

## Accessing the browserStack

After or during the execution of the tests, you can check the resources available in the browserstack.
Among which I can cite:

```
Text logs.
```

```
Visual logs.
```

```
Console logs.
```

```
Recorded video.
```

```
Network logs.
```

### To access all the features, do the following steps.

```
Access BrowserStack site: https://automate.browserstack.com/dashboard/v2/.
```

```
Sign in: user: amaurimoraismann@gmail.com, password: Serasa2022
```

```
Access the option: DASHBOARD
```

```
The results of all executions will be displayed, you could use filters like: project, user, build.
```

## Docker hub
1. Docker image jenkins
    - [amaurimann/missao-devops-jenkins](https://hub.docker.com/repository/docker/amaurinmann/missao-devops-jenkins)

2. Docker image Sonarqube
    - [amaurimann/integracao-continua](https://hub.docker.com/repository/docker/amaurinmann/integracao-continua)

## Versioning

Was used [Sourcetree](https://www.sourcetreeapp.com//) for versioning.

## Built With

* [SELENIUM WEBDRIVER](http://seleniumwebdriver.org/selenium-webdriver/) - The automation framework used
* [TestNG](https://testng.org/doc/documentation-main.html/) - The test framework used
* [MAVEN](https://maven.apache.org/) - Dependency Management
* [JAVA](https://www.oracle.com/technetwork/pt/java/javase/downloads/jdk8-downloads-2133151.html/) - Programing language
* [SonarLint](https://www.sonarlint.org/eclipse/) - Linter
* [BrowserStack](https://www.browserstack.com/) - BrowserStack is a cloud and mobile testing platform.
* [Jenkins](https://www.jenkins.io/) - Automation server
* [Docker](https://www.docker.com/) - Virtualization service
* [Sonarqube](https://www.sonarqube.org/) - Continuous Code Inspection

## Authors

* **Amauri Mann** - *QA Engineer* - [GitHub](https://github.com/amaurimann)

## License

This project is licensed under the GNU License.