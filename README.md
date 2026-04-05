# MeshCom-Reflector
The MeshCom reflector exchanges messages and information between the individual MeshCom country servers. The reflector does not apply any filters but receives the information directly from the country servers.

## MeshCom Server Network

| Servers | Transfer| Reflectors | Transfer | Dashboards |
| ----- | ----- | ----- | ----- | ----- |
| MeshCom-Server (DL) | <---------> | | | |
| MeshCom-Server (OE) | <---------> | | -----> | MAP |
| MeshCom-Server (I) | <---------> | MeshCom-Reflector | -----> | DashBoard |
| MeshCom-Server (HB) | <---------> | | -----> | LOGs |
| MeshCom-Server (more) | <---------> | | | |

## MeshCom Gateway Network
All MeshCom-Node-Gateways connect to a MeshCom-Server and send KEEP alive messages and check returned BEAT messages to check the MeshCom-Server is alive and UDP-Mesaaging is working.

### HEARD-BEAT
| Source | Protokoll | Destination | Port |
| ----- | ----- | ----- | ----- |
| MeshCom-Gateway | --> KEEP | MeshCom-Server | 1990 |
| MeshCom-Gateway | <-- BEAT | MeshCom-Server | 1990 |

### DATA
| Source | Protokoll | Destination | Port |
| ----- | ----- | ----- | ----- |
| MeshCom-Gateway | --> DATA | MeshCom-Server | 1990 |
| MeshCom-Gateway | <-- GATE | MeshCom-Server | 1990 |

## MeshCom Reflector Network

All MeshCom-Servers connect to the MeshCom-Reflector (one or more) and send LOGIN messages and check returned CONNECTED messages  to check the MeshCom-Reflector is alive.

### LOGIN
| Source | Protokoll | Destination | Port |
| ----- | ----- | ----- | ----- |
| MeshCom-Server | --> LOGN | MeshCom-Reflector | 6901 |
| MeshCom-Server | <-- CONN | MeshCom-Reflector | 6901 |

### CONNECTED
| Source | Protokoll | Destination | Port |
| ----- | ----- | ----- | ----- |
| MeshCom-Server | --> DATA | MeshCom-Refelctor | 6901 |
| MeshCom-Server | <-- GATE | MeshCom-Reflector | 6901 |
