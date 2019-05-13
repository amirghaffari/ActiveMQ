# ActiveMQ

This example shows how to use Spring boot to send messages through an external ActiveMQ server. For external ActiveMQ, `connectionFactory` is used to manage the connection to the external message broker. For connecting to the external ActiveMQ server, we need to specify a `url`, `username`, and `password`. The sender needs to configure the `JmsTemplate` to use the `connectionFactory` instead of the default one that uses the internal embedded message broker provided by Spring Boot. Also, the message receiver needs  to use the `connectionFactory`. To do that the `jmsListenerContainerFactory` is used to return a `DefaultJmsListenerContainerFactory` bean that using the `connectionFactory`.

We can access the ActiveMQ console (http://localhost:8161/admin/) to see all the messages and queues.
