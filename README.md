Xray End To End Integration With Lambdatest

Xray is a popular test management app for Jira that integrates seamlessly with Jira Software, Jira Core, and Jira Service Management. It's primarily used for managing and tracking testing activities within the Jira environment. It supports integration with various test automation frameworks such as Selenium, JUnit, and Cucumber. This allows teams to automate test execution and seamlessly incorporate automated test results into their testing workflows within Jira.

To get started you need to have an Xray app installed within your Jira

![](Aspose.Words.560fa477-aafb-4db0-941d-b98929160d72.001.png)

Now in order to further access, and push your test results over to x-ray you would firstly require a client\_id and client\_secret , for more reference please visit here: <https://docs.getxray.app/display/XRAYCLOUD/Authentication+-+REST>


In order to get the client\_id and client\_secretn and then get the bearer token you first need to click over apps and from the drop-down click over manage to apps, and then in the left hand click on API-Keys 

![](Aspose.Words.560fa477-aafb-4db0-941d-b98929160d72.002.png)


` `![](Aspose.Words.560fa477-aafb-4db0-941d-b98929160d72.003.png)

Then , you click on create api-key and start typing your username , once you get the valid username over the drop-down select that and click on generate

![](Aspose.Words.560fa477-aafb-4db0-941d-b98929160d72.004.png)

Now Please copy the client\_id and client\_secret in order to generate the bearer token, please use the below api in order to generate a bearer token

**curl -H "Content-Type: application/json" -X POST --data '{ "client\_id": "32A27E69B0AC4E539C1401643799E8E7","client\_secret": "d62f81eb9ed859e11e54356dd8a00e4a5f0d0c2a2b52340776f6c7d6d757b962" }'  <https://xray.cloud.getxray.app/api/v1/authenticate>**



You can use postman in order, to hit this curl just click on import and then go over to body and change the **client\_id** and **client\_secret** with yours and click on send then will generate a bearer token which can be used to push your code results further 

![](Aspose.Words.560fa477-aafb-4db0-941d-b98929160d72.005.png)


Create a new project once you have a bearer token, and copy the project\_key as that will be required in the future

![](Aspose.Words.560fa477-aafb-4db0-941d-b98929160d72.006.png)

Now once done please refer to the following api’s to push your test result: <https://docs.getxray.app/display/XRAYCLOUD/Import+Execution+Results+-+REST+v2#ImportExecutionResultsRESTv2-JUnitXMLresults>

Then we convert that api into a usable code format, and use that in the after method such once the execution is done . We can push our code over to the project we have created in Jira

![](Aspose.Words.560fa477-aafb-4db0-941d-b98929160d72.007.png)
