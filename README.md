# MeshCom-Reflector
The MeshCom reflector exchanges messages and information between the individual MeshCom country servers. The reflector does not apply any filters but receives the information directly from the country servers.

## MeshCom Network

| Servers | Transfer| Reflectors | Transfer | Dashboards |
| ----- | ----- | ----- | ----- | ----- |
| MeshCom-Server (DL) | <---------> | | | |
| MeshCom-Server (OE) | <---------> | | -----> | MAP |
| MeshCom-Server (I) | <---------> | MeshCom-Reflector | -----> | DashBoard |
| MeshCom-Server (HB) | <---------> | | -----> | LOGs |
| MeshCom-Server (more) | <---------> | | | |

### HEARD-BEAT
| Source | Protokoll | Destination |
| ----- | ----- | ----- |
| MeshCom-Server (...) | --> KEEP | MeshCom-Reflector |
| MeshCom-Reflector | <-- BEAT | MeshCom-Server |

### DATA
| Source | Protokoll | Destination |
| ----- | ----- | ----- |
| MeshCom-Reflector | <-- DATA | MeshCom-Server |
| MeshCom-Server (...) | --> GATE | MeshCom-Reflector |
