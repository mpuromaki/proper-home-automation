# prha - Proper Home Automation

ℹ️ Please note that this is still very much work in progress.

PRHA is a set of definitions and example implementations for setting up an powerful offline home automation system.

## Network overview

- IPv6-only network. ULA addressing.
- Isolated from generic and Wide-Area-Networks.
- Supports Redundancy.
- Automatic network configuration with IPv6 RA, ND, SLAAC.
- Automatic service discovery with mDNS
- 16-byte master secret.

![PRHA Network Overview](./prha-network-overview.drawio.svg)

## Nodes

### Proper Node

Proper Node is expected to:
- Be always available.
- Able to send messages to servers.
- Able to receive messages from servers.

### Sleepy Node

Sleepy Node is expected to:
- Be asleep most of the time.
- Able to send messages to servers.
- Able to receive messages from servers only for small window of time after transmitting.

## Discovery

Device and service discovery is implemented with mDNS and DNS-SD. For discovery it is expected that the Nodes work to find the servers, 
as that allows sleepy devices in mesh networks to conserve battery and have unstable addressing.

### Servers

Servers advertise their presence under ```_prha-srvr._udp.local```. Additionally they use 3-byte hex-encoded subtype derived
from ```master secret``` to differentiate overlapping networks.

For example a single server would advertise:
```
server_1._prha-srvr._udp.local
aabbcc._sub._prha-srvr._udp.local
```

## Protocol

Protocol is based on CoAP over UDP.
