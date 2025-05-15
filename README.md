## AdvProg 2024/2025 - Tutorial 09

## a. How much data your publisher program will send to the message broker in one run?  

The publisher program sends 5 `UserCreatedEventMessage` objects to the message broker in one run.

## b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean? 

Since the subscriber also has the same url, this means that both the subscriber and publisher are connecting to the same message broker instance that is running in the local machine. Just like in the subscriber, the first and second `guest` are used as credentials for authentication, while the `localhost:5672` part tells what is the hostname in which the application and message broker is running, as well as the port number.

## Running RabbitMQ Interface
![RabbitMq](assets/RabbitMq.png)

## Cargo run on both subscriber and publisher
![CargoRun](assets/CargoRun.png)
When the publisher is ran, messages are sent to the message broker, which is RabbitMQ in this case, which is then redirected to the subscriber and then shown in the subscriber terminal log. Since there are 5 message tranmission from publisher due to how it was setup, each of the message sent would be shown on the subscriber terminal log as separate responses, thus the 5 different lines on the subscriber log shown in the image.

## RabbitMQ Graph after running Cargo Run on Publisher
![RabbitMQCargoRun](assets/RabbitCargoRun.png)
The spike shown in the image is generated onto the graph each time an instance of the publisher is run. Since we are sending messages without queueing, the rate of the message is shown on the message rates graph, thus the spike.

## Slow Subscriber Graph Representation
![Slow Subscriber](assets/SlowSubscriber.png)
The metrics beside the queue message graph shows 35, which is the number of queued messages as I made the message requests. This is because I ran `cargo run` 7 times quickly thus causing the messages to be queue, with each run request queueing 5 messages. 