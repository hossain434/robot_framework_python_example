# robot_framework_python_example

Robot Framework:
1.	What is the purpose to use  this tool?
Robot Framework is a generic test automation framework for acceptance testing and acceptance test-driven development (ATDD). It has easy-to-use tabular test data syntax and it utilizes the keyword-driven testing approach.
Uses
Because of its flexibility, robot framework can be used to test desktop applications, web applications, mobile applications, and RESTful and SOAP-based services. Because it provides an abstraction layer on top of the physical implementation of the system under test, it is possible to write tests that work cross-platform (ie: the same test case could be used to test both an android and iOS app, or for testing a web app that runs on chrome, firefox and safari).

Although robot framework is often used to test browser-based applications, it has been used to test databases, mobile devices, calculators, and many other things.

Extensibility
One of the great strengths of the robot framework is that it is highly extensible. Many of the features mentioned above are implemented as libraries. For example, you can plug in a library to use selenium to drive a browser. You can plug in a database library to directly access databases. There are libraries to support testing desktop apps, services, and many more.
1)	Using  robot framework you can define Test cases

2) You can Create a seprate variable file and then pass it with main file during run time (check pybot -V)

3)You dont need to be worry about reporting part , all the reports would be generated and with better drill down options

Additional advantage

1) There are lots of inbuilt libraries, which will help you to do your task easily

2) You can create your own custom library and import in Robotframework

3) You would be able to drill down till last variable where the problem is with help of RobotFramework Reports, which will save lots of time
2. Why this is better than other tool?
Same as #1
2.	Why you're using this tool?
	Same as #1

4. Usability:
a. Normal scripting using page object (Yes) and with different browsers (Yes). and platform e.g Windows, MAC (Yes), Mobile (Yes) https://dzone.com/articles/mobile-test-automation-using-robot-framework
b. Parallel execution.(Yes)
c. Datadriven with Assertion using csv or xlsx (yes)
d. Jenkins build or execution in Docker  (Yes)
e. Result Report (built in report)
f. Advantages and drawback

I think the question should be: Java WebDriver + TestNG Vs Robot.

I have worked on both Java + TestNG and RobotFramework. Here is my analysis by points.

Ease of use
TestNG: You need to know Java & ANT/Maven, loggers and more libraries (depending on your need).

Robot: Basic programming language is enough in any language. You can train your manual testing team.

Winner: Robot

Code writing
TestNG: Basically, it is Java. Takes a bit more time compared to Robot. You need to write some extra lines which have nothing to do with your business. i.e. the definition of classes, scoping etc. However, people expert in writing code may argue here.

Robot: Write only as much as you need for your automation. (Standard login page code will not be more than 6 lines)

Winner: Robot

Parallel Execution
TestNG: Possible. You can do that with Selenium Grid or on Standalone machine

Robot: Possible (using pabot). You can use selenium grid too.

Winner: Tie

Logging and Failure Analysis
TestNG: If you are used to Java then it is easy. However, you don't get the logs as good/cool as Robot. I guess screenshot is not captured by default unless you implement some logic. you need to use Log4j for detailed logging.

Robot: Neat and clean logs and reports. Comes with a screenshot.

Winner: Robot

Flexibility
TestNG: This is Java. The Sky is the limit.

Robot: There are many things you can't do. if-else (only if block). No nested loops. And many things if you need complex coding. For many things, you can write a custom keyword in Python.

Winner: TestNG (Java)

Framework Design
TestNG: You have to design the framework.

Robot: It's a readily available framework

Winner: Robot

Resource Availablity
TestNG/Java: It is so easy to find a person who knows Java/TestNG. If you don't know Java, there are plenty of developer in dev team who can help the manual tester to begin. However, quality of code will vary depending on who is writing code.

RobotFramework: It is hard to find someone who has worked on RF. Though, the learning curve is very short compared to Java. All one need to know any programming knowledge. Basic knowledge of Python is needed if someone wants to write a customized library.

Winner: Java

Conclusion
In most of the cases, I feel Robot will do whatever you want to do. It's supportive libraries are increasing with time. You can do Web, API, Mobile, SSH, DB and many types of automation easily without knowing much in details.

Robot Framework setup:
https://www.tutorialspoint.com/robot_framework

https://www.youtube.com/watch?v=oY1JSpVk5ek&list=PLhW3qG5bs-L_yjwGfRkdySzVKCbV7ciaX

https://github.com/robotframework/robotframework/blob/master/INSTALL.rst

Install python2.7
Install pip: 
python -m pip install --upgrade pip

Install robot framework: 
python -m pip install robotframework

Install Selenium
python -m pip install --upgrade robotframework-seleniumlibrary

Copy and paste chromedriver.exe (75) here: C:\Python37\Scripts   & C:\Python27\Lib\site-packages
Set path env variable: C:\Python37\Scripts   & C:\Python27\Lib\site-packages

Install RED Robot Editor plugin in Eclipse
After RED plugin install on Eclipse Goto Window->Preference->robotframework ->Installed framework->make sure python path is configured.
Goto Window->Perspective->Open Perspective-> Open Robot Editor

File->Create Robot Project

Create Robot test suite (testrobot)

Paste below script (python) on testrobot.robot file

Automatically add library to red.xml (compare to pom.xml)by pressing Ctrl+1 on error.

*** Settings ***
Library    SeleniumLibrary
Library  OperatingSystem


*** Variables ***
${BROWSER}  chrome
${WEBSITE}  http://www.google.com

*** Test Cases ***

Browser test

    Open Browser    ${WEBSITE}  ${BROWSER}

Now run the script.
