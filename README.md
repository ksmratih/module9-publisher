1. How much data your publisher program will send to the message broker in one run?

    In one run, the publisher program will send 5 events to the message broker. Each event is a UserCreatedEventMessage containing a user_id and a user_name. Each message contains around 24 bytes, therefore the total data transmitted is 120 bytes.

2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?

    - The first `guest` is the username.
    - The second `guest` is the password.
    - `localhost` means the RabbitMQ server is running locally on the same machine.
    - `5672` is the default AMQP protocol port used by RabbitMQ.
    - Both publisher and subscriber need to connect to the same broker to exchange messages through the queue.

### RabbitMQ
![](images/rabbit.png)

### Consoles
![](images/event.png)

### RabbitMQ after running publisher
![](images/rabbit2.png)
The spikes in the RabbitMQ chart show the moment when the publisher sends events to the message broker. Each spike corresponds to a burst of messages being published during a single execution of the publisher program. This causes the message rate to temporarily rise, shown by the peak on the graph. After the messages have been sent, the graph returns to flat.