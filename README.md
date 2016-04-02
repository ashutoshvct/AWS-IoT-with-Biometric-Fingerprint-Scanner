# AWS-IoT-with-Biometric-Fingerprint-Scanner
eSSL X990 biometric fingerprint scanner connection for real-time attendance  
Hi,
I have an eSSL X990 Biometric Fingerprint Scanner.
I want to use it with AWS IoT to develop this environment but i don't know where to start.
Any Help is appriciated!!!
Here is the link to the device:
http://www.esslsecurity.com/product/x990.


#Three ways to achieve this :
1) Device -> Specialize Software -(MQTT/WebSocket/HTTP RESTful - Device Shadow)-> IoT.

2) Device -> Specialize Software -(HTTP RESTful)-> API Gateway -> Lambda funciton (to process data) -> DynamoDB.

3) Device -> Specialize Software -(Any TCP)-> EC2 instance (to process data) -> DynamoDB.

*There may be other ways too.

### Implementation Steps ##
1. In order to begin implementation of the AWS IoT service with your device, you will first have to connect it to a machine that is running the manufacturers SDK. I recommend referencing the device documentation or contacting the manufacturer of the device if you are unsure how to do this. 

2. Next you will need to identify what information is accessible from the SDK (i.e. user ID, date of login, thumbprint id and image, etc). This is the data that will need to be encapsulated in a JSON object and sent to AWS IoT.

3. The device will need to be registered with AWS IoT before you will be able to send data to the IoT Broker. For testing purposes, I recommend using our step-by-step guide on installing and configuring the MQTT.fx which utilizes the Mosquitto MQTT library . Once connected, you will be able to publish test data to a topic of your choice in order to verify the proper function of your Rules.

4. After completing the testing portion of your development, you can move on to working with real data. With the data prepared from step #2, a connection to the AWS IoT service will need to be established. This can be done with one of the following ways :

  a. MQTT Protocol 
  b. WebSocket Protocol
  c. REST API call
  d. AWS CLI (uses REST API)

5. With the connection established, you can start publishing messages to a topic of your choice so that they can be processed by the Rule Engine and sent to a DynamoDB table. This step should not change from #3, where you did you initial testing using MQTT.fx.

