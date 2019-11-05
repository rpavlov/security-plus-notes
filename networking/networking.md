# Network security

## Firewalling

Stateless firewall
Output request on open ports may receive a response on a different port and is dropped.

Stateful firewall
Ports are dynamically opened for the reply by keeping track of the request.

There are 4 different implementations
* Packet filtering routers (most basic)
* Screened-host firewall system (also implements the above)
* Screened-subnet firewall (implements a DMZ)
* Dual homed host firewall. Uses 2 network adapters.

## IDS

3 layers: preventive, detective, corrective.

IDS: intrusion detection system.
IPS: intrusion prevention system.

Snort is one of the major IDS. Firewallis is preventive, by contrast.

IDS are either signature based or behaviour based. Behaviour based needs to run, build a baseline or heuristic and alert based on that. Lot of false positives and if its compromised to begin with are problematic.

IDS are either network based or host based. The later is used from event viewer or logs, whereas network is based on real traffic.


