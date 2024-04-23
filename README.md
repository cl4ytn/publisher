1. How many data your publisher program will send to the message broker in one run?
The publisher program sends five UserCreatedEventMessage instances to the message broker in one run. Each message has a user_id to uniquely identify a user, and a user_name representing the name of the user. These messages are sent to the broker using the publish_event method of the CrosstownBus instance p. The program demonstrates the creation of messages for different users with IDs 1 to 5 and their respective names. Each message triggers an event type "user_created", to indicate that a new user has been created.

2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
Because the subscriber and publisher programs share the same url, it means that they are both communicating with the same RabbitMQ message broker instance. This allows them to exchange messages because they are apart of the same system. The publisher is responsible for sending messages to the message broker. The subscriber is responsible for receiving and processing the messages from the message broker. The URL allows the two programs to connect and communicate via the same messaging backend.

- Running Rabbitmq
![alt text](images/rabbitmq.png)

- Sending and processing event

![alt text](images/terminals.png)
Because both programs share the same URL amqp://guest:guest@localhost:5672, they connect to the same AMQP message broker. Over that message broker, the publisher sends messages and the subscriber receives them. UserCreatedEventMessage objects are published to the user_created queue by the publisher program. When the user_created queue gets messages, the subscriber program prints each one. Note that each object comes with a user_id and user_name to identify the user of that instance.

- Monitoring chart based on publisher
![alt text](images/rabbitmq2.png)
The first graph shows the queued messages that the publisher sends to the message broker. The second graph shows the weight of the messages sent by the publisher with respect to the rate at which they are sent. The two graphs visualize the relation between published and received messages in real time. The purple spikes are the Consumer acks and the yellow spikes are the publishes. This allows us to get a concise understanding of how the publisher and subscriber programs interact with each other.