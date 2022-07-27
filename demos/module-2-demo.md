# Using Spring Boot 2 With Spring Initializr - Module 2 Demonstration

This page provides details for the module 2 demonstration of the "Using Spring Boot 2 With Spring Initializr" Pluralsight course.

## Project Links

* Spring Initializr Web UI: https://start.spring.io

## Demo Script - Exploring Your First Initializr Generated Project

1. I've opened the Spring Initializr website at start.spring.io. The goal of this demonstration is to create a back-end domain service for the fictional company Globoticket. The service will target APIs for their customer domain. When creating a new Spring Boot project in Initializr, I often start with the project meta-data section. First, I'll define the group name. Given that the company's website domain is globoticket.com and this is the first of many services, I'll enter the group name as com.globoticket.service
       ```
       com.globoticket.service
       ```
2. Once I entered the group name, you may have noticed that Initializr updated the package name to match the group name. Next, I define the artifact. The back-end service I'm creating will provide APIs for the customer domain; therefore, I'll name the artifact customer-service.
       ```
       customer-service
       ```
3. Again, you may notice that the form values have changed. The artifact name is used to update the project name and package name. Now, I'll set the project name. I'll use the name CustomerService, without spaces.
       ```
       CustomerService
       ```
4. This value will be used as the prefix for the spring application class name and the prefix for the test class name. Next, I define the project description. I can add a simple description for now. The value will be set in the build script's description field. I'll use the description Globoticket Customer Service
       ```
       Globoticket Customer Service
       ```
5. Now, I'll define the package name. The package name can be set to com.globoticket.service.customer
      ```
      com.globoticket.service.customer
      ```
6. I'm going to leave the packaging selection as a JAR file. I'll also leave the default selection for the version of Java. With the project meta-data filled out, let's view the project explorer by clicking the explore button. This will open a modal where you can explore the impacts of your meta-data entries on the generated project. 
7. Let's start by reviewing the impacts to the build script. Select the Maven pom.xml file if it's not already selected. 
8. Let's highlight each impact to the file from the meta-data. First, here is the group name that I entered. Next, the artifact I entered is used as the artifact ID. The project name is stored in the name element. The description is stored in the description element. And finally, a build property of Java version is set to the version number I selected. Next, let's review the impacts to the source code. Start by expanding the source folder to display the folders for the main application class and main test class.
9. Select the main class of Customer Service Application. 
10. This is the Spring Boot application class. The class name uses a prefix based on the project name entered. Next, select the main test class. 
11. Similarly, the class name of the test class uses the same prefix based on the project name. Click the close button to close out the project explorer modal. 
12. While I won't be packaging the project as a WAR file, it may be helpful to understand the impact to Initializr when its selected. Select War as the packaging for the project.
13. Click the explore button to open the project explorer
14. Then, navigate to the Maven pom.xml file.
15. If you choose War as the packaging option, an additional element of packaging is added to the script. The value is set to War.
16. Also, notice that the starter dependency has been updated to spring boot starter web.
17. An additional dependency was added for Tomcat. Now, expand the source folder.
18. An additional class was added named ServletInitializer. This supports the initialization of the web application using Spring Boot's servlet initializer implementation. 
19. Finally, Initializr has added two folders to the resources directory to serve web content. Selecting War has resulted in Initializr taking opinions for you on dependencies and project structure, even though you didn't select a Web dependency from the form. Click the close button to return to the main form.
20. Change the War packaging back to a Jar. 
21. This completes the project meta-data for the Globoticket customer service. The next section that I need to consider is the project type. I'll start by showing you the impact of selecting Gradle, then the impact of selecting Maven. To start, click the Gradle Project option.
22. Then, open the project explorer to view the changes.
23. Selecting Gradle has significantly changed the generated project folders and files. Instead of a Maven pom.xml file, a Gradle build script is now available. The gradle wrapper and gradle command have been included. And finally, a Gradle settings file has been added. Select the build.gradle file.
24. This is the build script Initializr generates for you. It includes the foundational plugins and dependencies for a Spring Boot project. The source classes and properties have all remained the same. Let's close the explorer modal.
25. Change the project type back to a Maven project.
26. Now, open the explorer modal again.
27. For a Maven project type, Initializr includes several files and folders to support builds. First, the maven wrapper is included. A Maven pom.xml file is added to the project. And finally, the Maven command is included. Open the Maven pom.xml file.
28. Similar to the Gradle script, the foundational dependencies and plugins have been included. Close the project modal again.
29. As the standard for Globoticket is to use Maven for builds, I have the right project type selected for the customer service. Now, I need to consider the language for the customer service. While the standard will be Java, it's useful to understand the impact of changing this selection. Select Kotlin as the language.
30. Then, open the project explorer again to view changes.
31. Select the Maven pom.xml file.
32. By selecting Kotlin, the pom file was updated. 
33. A new property has been added named kotlin version. It's set to the most recent version of Kotlin
34. Several dependencies have been added to support Kotlin development, build and runtime.
35. Finally, the build directories and plugins have been updated to support Kotlin. Now, expand the source directory.
36. Select the customer service application class.
37. Initializr has now generated a file that uses the Kotlin language instead of Java. Close the project modal.
38. You can now see the impact that language selection has on Initializr project generation. Revert the language change by selecting Java. 
39. This completes the language selection for the customer service. As this course is only covering Spring Boot 2, I'll leave the default selected version for the customer service. At this point, the Customer Service meta-data, project type, language and spring boot version are all set. Now, I can add dependencies to the customer service in an iterative fashion. Click on the Add Dependencies button to open the dependencies modal. 
41. I want to begin the project with a minimal number of dependencies. Commonly, I start by selecting two of the developer tool libraries. Select Spring Boot Dev Tools for features that include live reloads.
42. Select Spring Configuration Processor for features like contextual help on application properties.
43. As the customer service will be serving REST APIs, the only additional dependency I'll select is Spring Web.
44. Return to the main initializr form if you multi-selected the dependencies and the modal is still open.
45. With dependencies added, I can now generate the project and import it in an IDE. Click the generate button to download the project.
46. This will generate and download a zip file. Extract the zip file to any directory you want. The next part of this course will demonstrate importing the project into an IDE.


49. I have the main dashboard of IntelliJ opened. I'm going to import the project to use as my baseline customer service. I'll start by clicking the Open button.
50. I extracted the zip file of the project to C:\dev\customer-service. I'll enter this as the folder and click Ok.
51. IntelliJ will import the project, build it and synchronize dependencies. Open the Maven pom.xml file.
52. Here you see the three dependencies that were selected. As a last step, expand the source directory to open the CustomerServiceApplicationTests class.
53. Run the test. 
54. The test should successfully load the Spring context. This completes importing the project into the IDE. At this point, I have the baseline project for my Initializr strategy. A viable next step would be to create a simple GET endpoint in a REST controller. Then, create a mock MVC test to verify the endpoint. Let's return to the Initializr website.



55. With my baseline project in place, I can now iteratively add dependencies. Let's assume my next step is to secure the REST endpoint I created. I'll add the Spring Security library to help accomplish this. Open the Add Dependencies modal.
56. Search for the text Spring Security.
57. This results in several dependencies related to security. Select the Spring Security dependency.
58. Open the project explorer.
59. Select the Maven pom.xml file. 
60. Two dependencies have been added to the build. First is the spring security starter library.
61. The second is the spring security test library.If I copy these two dependencies into my baseline project's pom.xml file, what do you think will happen? The project will build successfully; however, the mock MVC test I created will likely fail. When the Spring Security dependency was added, Spring Boot defaulted to secure the endpoint, which should result in an unauthorized error for your test. At this point, I can configure security in the project and fix the broken test. Once security configuration is complete, I can select and include the next dependency. Once all the dependencies have been added, the Globoticket customer service will be ready to go for adding business functionality. Hopefully this showed you how easy and intuitive it is to get a new Spring Boot 2 project up and running with Initailizr. That concludes the demonstration. 
