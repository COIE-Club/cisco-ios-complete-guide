<div align="center">

<h1>Cisco IOS Ethernet Interfaces</h1>

Learn how to configure and verify Ethernet interfaces on Cisco IOS routers.

</div>

---

# Overview

Ethernet interfaces are the foundation of IP connectivity in Cisco networks. Before implementing routing protocols, VLANs, security, or any advanced technology, network devices must first establish Layer 1 and Layer 3 connectivity through properly configured interfaces.

In this lab, two Cisco ISR4331 routers are directly connected using their Gigabit Ethernet interfaces. The objective is to configure IPv4 addresses, enable the interfaces, verify connectivity, and understand the operational status of Ethernet interfaces in Cisco IOS.

---

# Why it is Important

Every Cisco router deployment begins with interface configuration.

Without properly configured interfaces:

- Routers cannot communicate with neighboring devices.
- Routing protocols cannot form adjacencies.
- Management access (SSH, Telnet, SNMP, etc.) will not function.
- Network troubleshooting becomes significantly more difficult.

Understanding Ethernet interfaces is one of the most fundamental skills required for:

- CCNA
- CCNP Enterprise
- Enterprise Network Administration
- Data Center Networking
- ISP Networks

In production environments, verifying interface status is usually the first troubleshooting step whenever connectivity issues occur.

---

# Topology

<div align="center">

![topology](./topology.png)

### Device Connections

| Device | Interface | Connected To | Interface |
|---------|-----------|--------------|-----------|
| R1 | GigabitEthernet0/0/0 | R2 | GigabitEthernet0/0/0 |

### IP Addressing

| Device | Interface | IP Address | Subnet Mask |
|---------|-----------|------------|-------------|
| R1 | GigabitEthernet0/0/0 | 10.10.10.1 | 255.255.255.252 |
| R2 | GigabitEthernet0/0/0 | 10.10.10.2 | 255.255.255.252 |

</div>

---

# Requirements

- Cisco IOS Router (ISR4331 or equivalent)
- Cisco Packet Tracer
- Basic knowledge of Cisco IOS CLI
- Ethernet connection between the two routers

---

# Configuration

## Configure R1

```text
enable

configure terminal

hostname R1

interface GigabitEthernet0/0/0
 ip address 10.10.10.1 255.255.255.252
 no shutdown

end

write memory
```

---

## Configure R2

```text
enable

configure terminal

hostname R2

interface GigabitEthernet0/0/0
 ip address 10.10.10.2 255.255.255.252
 no shutdown

end

write memory
```

---

# Configuration Explanation

## hostname

```text
hostname R1
```

Changes the router's hostname.

Using meaningful hostnames is considered a best practice because it makes troubleshooting, documentation, logging, and network management significantly easier in enterprise environments.

---

## interface

```text
interface GigabitEthernet0/0/0
```

Enters Interface Configuration Mode.

Any command entered afterward affects only the selected interface.

---

## ip address

```text
ip address 10.10.10.1 255.255.255.252
```

Assigns an IPv4 address and subnet mask to the interface.

The `/30` subnet is commonly used for point-to-point links because it provides exactly two usable host addresses, making efficient use of IPv4 address space.

---

## no shutdown

```text
no shutdown
```

By default, Cisco router interfaces are administratively disabled.

The `no shutdown` command enables the interface, allowing it to begin transmitting and receiving Ethernet frames.

Without this command, the interface remains in an **administratively down** state regardless of the physical connection.

---

## write memory

```text
write memory
```

Saves the running configuration to the startup configuration.

Without saving, all configuration changes are lost after the router reloads.

Equivalent command:

```text
copy running-config startup-config
```

---

# Verification

## Verify Interface Status

```text
show ip interface brief
```

Example output:

```text
Interface              IP-Address      OK? Method Status Protocol

GigabitEthernet0/0/0   10.10.10.1      YES manual up     up
```

Both the **Status** and **Protocol** fields should display **up**.

---

## View Detailed Interface Information

```text
show interfaces GigabitEthernet0/0/0
```

Useful information includes:

- Interface state
- Hardware type
- MAC address
- MTU
- Bandwidth
- Duplex
- Speed
- Input/output packets
- Error counters
- CRC errors
- Interface resets

This command is one of the most commonly used troubleshooting tools in enterprise networks.

---

## Verify IP Configuration

```text
show running-config interface GigabitEthernet0/0/0
```

Displays only the configuration applied to the interface.

---

## Test Connectivity

From R1:

```text
ping 10.10.10.2
```

Expected result:

```text
!!!!!
```

Five exclamation marks indicate that all ICMP echo requests were successful.

---

# Common Mistakes

| Mistake | Result |
|----------|--------|
| Forgetting `no shutdown` | Interface remains administratively down |
| Incorrect subnet mask | Devices cannot communicate |
| Incorrect IP address | Ping fails |
| Connecting the wrong interfaces | Physical link remains down |
| IP address conflict | Unpredictable connectivity issues |
| Forgetting to save the configuration | Configuration is lost after reboot |

---

# Troubleshooting

If the routers cannot communicate, perform the following checks:

### Check Interface Status

```text
show ip interface brief
```

Verify that both **Status** and **Protocol** are **up**.

---

### Verify Physical Interface Details

```text
show interfaces GigabitEthernet0/0/0
```

Look for:

- Input errors
- CRC errors
- Interface resets
- Link state
- Speed and duplex

---

### Verify IP Addressing

```text
show running-config interface GigabitEthernet0/0/0
```

Ensure the configured IP address and subnet mask are correct.

---

### Test Connectivity

```text
ping 10.10.10.2
```

If the ping fails:

- Confirm the interfaces are enabled.
- Verify both routers are in the same subnet.
- Check that the Ethernet connection is correct.
- Ensure there are no duplicate IP addresses.

> **<span style="color:#e74c3c;">Important:</span>** An interface showing **up/down** usually indicates a Layer 2 issue, while **administratively down/down** indicates the interface has not been enabled with `no shutdown`.

---

# Best Practices

- Always configure meaningful hostnames.
- Use a consistent IP addressing scheme.
- Enable interfaces immediately after assigning IP addresses.
- Verify interface status before troubleshooting higher-layer protocols.
- Save the configuration after making changes.
- Regularly monitor interface statistics for errors or packet drops in production environments.
- Use `show interfaces` as one of the first commands during connectivity troubleshooting.

---

# References

Cisco Command Reference: [IP Commands](https://www.cisco.com/c/en/us/td/docs/server_nw_virtual/2-5_release/command_reference/ip.html)
Cisco Command Reference: [Chapter: Ethernet Interface Commands](https://www.cisco.com/c/en/us/td/docs/iosxr/cisco8000/Interfaces/b-interfaces-hardware-component-cr-8000/ethernet-interface-commands.html)
