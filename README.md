1. How many data your publisher program will send to the message broker in one run?
The publisher program sends five UserCreatedEventMessage instances to the message broker in one run. Each message has a user_id to uniquely identify a user, and a user_name representing the name of the user. These messages are sent to the broker using the publish_event method of the CrosstownBus instance p. The program demonstrates the creation of messages for different users with IDs 1 to 5 and their respective names. Each message triggers an event type "user_created", to indicate that a new user has been created.

2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
Because the subscriber and publisher programs share the same url, it means that they are both communicating with the same RabbitMQ message broker instance. This allows them to exchange messages because they are apart of the same system. The publisher is responsible for sending messages to the subscriber. The subscriber is responsible for receiving and processing the messages that the publisher sends. The URL allows the two programs to connect and communicate via the same messaging backend.

- Running Rabbitmq
![alt text](rabbitmq.png)
![alt text](terminals.png)
[Describe this screenshot]
![alt text](rabbitmq2.png)
[Describe this screenshot]
![alt text](rabbitmq3.png)
Answer why the total number of queue is as such (in my machine is 20, what about yours?)
![alt text](rabbitmq4.png)
[Describe this screenshot]