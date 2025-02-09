# CSharp Dapr Sample with Kafka

This example shows how to run Dapr in CSharp with Kafka and Minimal APIs.

### Run Kafka

First, make sure you have Docker installed so you can run Kafka locally.

```bash
docker compose up -d
```

### Run the subscriber

```bash
export PATH=$HOME/.dotnet:$PATH
cd subscriber
dapr run --app-id subscriber --app-port 5141 --resources-path ./components -- dotnet run
```

### Run the publisher

```bash
cd publisher
dapr run --app-id publisher --resources-path ./components -- dotnet run
```

### Observe the event

In your subscriber app you should see:

```bash
== APP == 17
```