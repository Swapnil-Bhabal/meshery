---
layout: default
title: Troubleshooting Meshery Installations
description: Troubleshoot Meshery installation and deployment
permalink: guides/troubleshooting/installation
type: Guides
category: troubleshooting
---

## Meshery's Preflight Checks

Anytime a `mesheryctl system` command is executed, a series of preflight checks are run. An attempt will be made to connect to the Kubernetes cluster configured in the user's kubeconfig as their current-context .

1. Check whether `mesheryctl` can initialize a Kubernetes client.

    Situation: `mesheryctl` fails to query for pods in the default namespace of the user's current Kubernetes context.

2. Remove `~/.meshery` to reinitialize Meshery

    Situation: Unable to start Meshery Server with `make run-local` due to error of `key/value size is invalid`

## Meshery Operator

### Meshery Broker
Example of a healthy Meshery Broker server with an actively connected (subscribed) Meshery Server:

```
➜  ~ kubectl logs -n meshery meshery-broker-0 nats
[8] 2021/09/08 21:46:03.070952 [INF] Starting nats-server version 2.1.9
[8] 2021/09/08 21:46:03.070982 [INF] Git commit [7c76626]
[8] 2021/09/08 21:46:03.071308 [INF] Starting http monitor on 0.0.0.0:8222
[8] 2021/09/08 21:46:03.071370 [INF] Listening for client connections on 0.0.0.0:4222
[8] 2021/09/08 21:46:03.071512 [INF] Server id is NAAYJNX4LDDNXW5UE7IP7PRQR2W2JP546XSFNUWQQHN7JYY27RG47KSG
[8] 2021/09/08 21:46:03.071516 [INF] Server is ready
```
For details about the state of the Meshery Server subscription see the http monitor port on Meshery Broker.

#### See Also

- [Error Code Reference](/reference/error-codes)

## Meshery Remote Providers

Once Meshery is installed, the remote provider "Meshery" can be chosen from UI or by using the command `mesheryctl system login`:

![Providers](/assets/img/providers/provider_screenshot.png)

```
➜  ~ mesheryctl system login
Use the arrow keys to navigate: ↓ ↑ → ←
? Select a Provider:
  ▸ Meshery
    None
```

If you cannot see "Meshery" Remote Provider and find such error logs in Meshery Server's logs (`mesheryctl system logs`), please make sure that Meshery Server is able to reach "https://meshery.layer5.io" in order to initialize the "Meshery" Remote Provider.

```
time="2021-11-10T11:05:30Z" level=error msg="[Initialize Provider]: Failed to get capabilities Get \"https://meshery.layer5.io/v0.5.71/capabilities?os=meshery\": dial tcp 3.140.89.205:443: i/o timeout"
```

For more details about Meshery Providers: 
- [Extensibility: Providers](/extensibility/providers)