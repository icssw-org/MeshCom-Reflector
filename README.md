# MeshCom-Reflektor
The MeshCom reflector exchanges messages and information between the individual MeshCom country servers. The reflector does not apply any filters but receives the information directly from the country servers.

## MeshCom Network

MeshCom-Server (DL) <------------------->
MeshCom-Server (OE) <------------------->                                                      -----> MAP
MeshCom-Server (I) <--------------------> <===> MeshCom-Reflector <==> MeshCom-Dashboards ===> -----> DashBoard
MeshCom-Server (HB) <------------------->                                                      -----> LOGs
MeshCom-Server (more) <----------------->
