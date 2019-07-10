# Image-Server-QA

## How to deploy the project

Pre-requisites
* Java
* Maven
* Cloud Foundry client 
https://docs.cloudfoundry.org/cf-cli/install-go-cli.html
* MongoDB service instance running in Cloud Foundry

## How to deploy the service
1. Checkout the code and import the project as a maven project
2. modify the ```manifest.yml``` with preferred host name and MongoDB service name in the Cloud Foundry
3. Go to the root directory of project and run ```mvn package``` to build the project
3. Run ```cf login``` to login to your Cloud Foundry space
4. Select the desired space in the Cloud Foundry
5. Run ```cf push``` to push the application to the Cloud Foundry 

Upon the successful deployment of the service, you will see the application url in terminal

## How to use the service
* Use a ```POST``` request to the endpoint with key ```image``` and image attached
* You will get a ```UUID``` key upon successful save of the image
* An image can be retrieved from the service by issuing a ```GET``` with parameter ```key``` and the value of the key you got when saving the image 
