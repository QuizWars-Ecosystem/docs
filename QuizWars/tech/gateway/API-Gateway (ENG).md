#quizwars #gateway #go #grpc #http #websocket 

**Link:** [GitHub](https://github.com/QuizWars-Ecosystem/api-gateway)

The Gateway acts as an intermediary between clients and services within the perimeter. It serves as the entry point for requests and is responsible for tracking all services and their addresses while handling request balancing.

Since our primary communication format is _gRPC_, the Gateway accepts requests on the _gRPC port_ and forwards them to the healthy instances corresponding to the requested destination.
#### Consul

It's important to understand that the Gateway itself does not verify service health—this task falls to _Consul_. When a service becomes operational, it registers itself in the _Consul_ registry, providing its address and port so that Consul can periodically check its status. If a service crashes or shuts down properly, _Consul_ removes it from the list of healthy services to prevent the _Gateway_ from accidentally routing requests to a non-functional instance.

The list of active services can be viewed in the _Consul_ dashboard. You can access it by navigating to the external address of the running container—typically _[http://localhost:8555](http://localhost:8555/)_. For precise details, check the port in [[Server Table# Default ports table]] or inspect the running container directly.

![[Pasted image 20250421231254.png]]

Here, we see one _Consul_ instance and two services, each with a single instance.

We can delve deeper by clicking on any service to view more detailed information.

![[Pasted image 20250421231611.png]]

This section displays the list of instances for the selected service, including their addresses, tags, and health status. At regular intervals, _Consul_ sends requests to the services to verify their operational status. If a service is healthy, Consul updates its records accordingly. If not, it retries a few times before ultimately removing the instance from the active list.

The _Gateway_ itself monitors the available service addresses via _Consul plan_. A _plan_ is essentially a subscription to events — our _Gateway_ subscribes to the addresses it needs. If changes occur (e.g., a new service instance is added), the Gateway updates its internal list to distribute requests across the available instances.