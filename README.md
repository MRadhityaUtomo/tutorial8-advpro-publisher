a. How many data your publisher program will send to the message broker in one
run?
publisher_event is called 5x. For each call it sends `UserCreatedEventMessage` dengan `user_id` and `user_name`. The event message is formatted as such: <br>
    1. User ID: "1", Nama Pengguna: "2206830744-Amir" <br>
    2. User ID: "2", Nama Pengguna: "2206830744-Budi" <br>
    3. User ID: "3", Nama Pengguna: "2206830744-Cica" <br>
    4. User ID: "4", Nama Pengguna: "2206830744-Dira" <br>
    5. User ID: "5", Nama Pengguna: "2206830744-Emir" <br>
<br>
b. The url of: `amqp://guest:guest@localhost:5672` is the same as in the subscriber program, what does it mean?
Having both programs have the url means they are connected to the same AMQP broker with identical credentials and address. The URL specifies the AMQP protocol, username, password, and the address + port of the broker. This makes it so both programs communicate through the same messaging system. It establishes a unified communication pathway for data exchange between the publisher and subscriber.

<br>
<br>

Running RabbitMQ as Message Broker.
![alt text](Screenshots/rabbitmq.png)

<br>

Screen show consoles after running publisher multiple times
![alt text](Screenshots/sending.png)
After the publisher program is run, data from the publisher side (hardcoded via main code) will be sent through the message queue. The subscriber program will receive these data from the message queue and show the message of the data formatted above.

<br>

Monitoring chart based on publisher
![alt text](Screenshots/messagerates.png)
The spikes or mounds show how there is a surge of message rates upon a certain timeframe. This is because cargo run was ran on the publisher program repeatedly. This will be visualized through the RabbitMQ message queue chart.