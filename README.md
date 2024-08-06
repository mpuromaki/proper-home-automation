# prha - Proper Home Automation

PRHA is a set of definitions and example implementations for setting up an powerful offline home automation system.

# Network overview

- IPv6-only network. ULA addressing.
- Isolated from generic and Wide-Area-Networks.
- Supports Redundancy.
- Automatic network configuration with IPv6 RA, ND, SLAAC.
- Automatic service discovery with mDNS

![PRHA Network Overview](./prha-network-overview.drawio.svg)

# Nodes

## Proper Node

Proper Node is expected to:
- Be always available.
- Able to send messages to servers.
- Able to receive messages from servers.

## Sleepy Node

Sleepy Node is expected to:
- Be asleep most of the time.
- Able to send messages to servers.
- Able to receive messages from servers only for small window of time after transmitting.
