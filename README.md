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
The MeshCom gateways connect to a MeshCom Server and send KEEP alive messages and check returned BEAT messages to check the MeshCom Server is alive and UDP-Mesaaging is working.

### HEARD-BEAT
| Source | Protokoll | Destination |
| ----- | ----- | ----- |
| MeshCom-Gateway | --> KEEP | MeshCom-Server |
| MeshCom-Gateway | <-- BEAT | MeshCom-Server |

### DATA
| Source | Protokoll | Destination |
| ----- | ----- | ----- |
| MeshCom-Gateway | --> DATA | MeshCom-Server |
| MeshCom-Server (...) | --> GATE | MeshCom-Gateway |
