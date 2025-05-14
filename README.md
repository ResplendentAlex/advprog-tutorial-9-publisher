## AdvProg 2024/2025 - Tutorial 09

## a. How much data your publisher program will send to the message broker in one run?  

The publisher program sends 5 `UserCreatedEventMessage` objects to the message broker in one run.

## b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean? 

Since the subscriber also has the same url, this means that both the subscriber and publisher are connecting to the same message broker instance that is running in the local machine. Just like in the subscriber, the first and second `guest` are used as credentials for authentication, while the `localhost:5672` part tells what is the hostname in which the application and message broker is running, as well as the port number.