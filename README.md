# AWS-IoT-with-Biometric-Fingerprint-Scanner
eSSL X990 biometric fingerprint scanner connection for real-time attendance  
Hi,
I have an eSSL X990 Biometric Fingerprint Scanner.
I want to use it with AWS IoT to develop this environment but i don't know where to start.
Any Help is appriciated!!!
Here is the link to the device:
http://www.esslsecurity.com/product/x990


#There can be many ways to achieve this, but as per my knowledge i know 3 ways:
1) Device -> Specialize Software -(MQTT/WebSocket/HTTP RESTful - Device Shadow)-> IoT ... 

2) Device -> Specialize Software -(HTTP RESTful)-> API Gateway -> Lambda funciton (to process data) -> DynamoDB

3) Device -> Specialize Software -(Any TCP)-> EC2 instance (to process data) -> DynamoDB
