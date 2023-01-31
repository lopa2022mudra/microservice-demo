
# A Microservice Demo using spring boot, spring Netflix Eureka & spring Cloud Gateway 

## Architecture of this demo microservice

   ![ms-demo drawio (1)](https://user-images.githubusercontent.com/32014166/215348269-60985498-35be-4269-a2b9-3c867083860e.png)


## Java Version
Used open-jdk **version 17** (https://openjdk.org/projects/jdk/17/)

## Build Tool
### We are using maven tool to build the project. You can download & install maven from official website (https://maven.apache.org/install.html)

## Making the build
### Download the source code using git ssh or https from https://github.com/lopa2022mudra/microservice-demo

#### - [x] **Check if maven is installed by putting 'mvn' command in command prompt or terminal**
* Go the root directory i.e; **microservice-demo**
* Use command ```mvn clean package```. Upon successful build creation will show below like screenshot
   
   ![image](https://user-images.githubusercontent.com/123809223/215835916-69d95e01-d2c8-402c-b351-c15d6bf1c6f1.png)

* All the necessary jars (microservice builds) should be created by now

* Start the Eureka Server for service discovery i.e; **microservice-discovery-server** by providing the following command

     <img width="237" alt="Screenshot 2023-01-30 at 3 41 29 AM" src="https://user-images.githubusercontent.com/32014166/215358484-6b2d8cdd-b558-4ae3-9ecf-bae3e363adea.png">

     
   ```java -jar microservice-discovery-server/target/discovery-1.0.jar```
   
   Upon successful start of the discovery server, you should see the something as below
   
   <img width="1423" alt="Screenshot 2023-01-29 at 7 40 26 PM" src="https://user-images.githubusercontent.com/32014166/215332110-fd1bfd28-e3f0-480e-9ada-768024024d71.png">
* We can access the default dashboard of Eureka Server
  at http://localhost:8761/
  
  <img width="1427" alt="Screenshot 2023-01-29 at 7 45 40 PM" src="https://user-images.githubusercontent.com/32014166/215332375-68bc4f0d-0b99-47de-a6ba-2140a42502a9.png">

* Now, start the VAT microservice in port 8081 & port 8082 using following command
     
     
     <img width="270" alt="Screenshot 2023-01-30 at 3 41 37 AM" src="https://user-images.githubusercontent.com/32014166/215358464-6d8e107c-2bb8-4f58-a14b-4fc4ebcc6d70.png">
     


   ```java -jar -Dserver.port=8081 microservice-vat-service/target/vat-1.0.jar```
   
   ```java -jar -Dserver.port=8082 microservice-vat-service/target/vat-1.0.jar```
   
      
      
      
   <img width="178" alt="Screenshot 2023-01-30 at 3 41 46 AM" src="https://user-images.githubusercontent.com/32014166/215358820-0a9350f2-93ce-44c3-9884-1758912cd84c.png">
   
   

   
   ```java -jar -Dserver.port=8080 api-gateway/target/gateway-1.0.jar```
   

* The VAT microservices will be auto registered to the service discovery and we can see it at http://localhost:8761/

![image](https://user-images.githubusercontent.com/123809223/215836332-2fa2d484-8bee-47cd-ac72-be22e95f41b7.png)


* You can view the API doc using swagger-ui at http://localhost:8081/swagger-ui/index.html

  
<img width="1308" alt="Screenshot 2023-01-29 at 1 39 55 AM" src="https://user-images.githubusercontent.com/32014166/215358655-769c3645-dd61-4151-801d-a832f4d08cd5.png">

