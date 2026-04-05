# Protocolls

## MeshCom-Node <--> MeshCom-Server

### KEEP

The KEEP message initiates the connection of a MeshCom-Node-Gateway to the MeshCom-Server.

| Element | type | Format  | Info |
| -------- | ------- |------- |------- |
| TYPE| fixed 4 (s) | KEEP | keyword |
| NODE-HEX-ID | fixed 8 (x) | "F03C1582" | last 4 bytes |
| NODE-Callsign |  fixed 9 (s) | "OE1KBC-12" filup | with blank |
| FW-VERSION |  fixed 4 (s) | 4.35 | |
| FW-SUB-VERSION |  fixed 1 (s) | p | |
| Booked groups |  variable (s) (0x00) | 20;232;262; | separeted by semicolon end with hex 0x00 |

### BEAT

Answer from MeshCom-Server to MeshCom-Node-Gateway following a KEEP-Message

| Element | type | Format  | Info |
| -------- | ------- |------- |------- |
| TYPE| fixed 4 (s) | BEAT | keyword |
| separation| fixed 1 (b) | 0x00 | |
| GATEWAY-Callsign length |  fixed 1 (b) | 0x00-0xFF | length of following GATEWAY-callsign |
| GATEWAY-Callsign |  variable (s) | "OE1KBC-12" | |

### DATA

Message transfer from MeshCom-Node-Gateway to MeshCom-Server (POS, TXT, HEY)

| Element | type | Format  | Info |
| -------- | ------- |------- |------- |
| TYPE| fixed 4 (s) | BEAT | keyword |
| NODE-HEX-ID | fixed 8 (x) | "F03C1582" | last 4 bytes |
| NODE-Callsign |  fixed 9 (s) | "OE1KBC-12" filup | with blank |
| FW-VERSION |  fixed 4 (s) | "4.35" | |
| FW-SUB-VERSION |  fixed 1 (s) | "p" | |
| RSSI |  fixed 4 (9) | "0009" | data heard with |
| SNR |  fixed 4 (9) | "0009" | data heard with |
| PLAYLOAD length |  fixed 1 (b) | 0x00-0xFF | length of following payload-bytes |
| PLAYLOAD |  variable (b) | 0x00-0xFF | payload-bytes |

### GATE

Message transfer form MesgCom-Server to MeshCom-Node-Gateway

| Element | type | Format  | Info |
| -------- | ------- |------- |------- |
| TYPE| fixed 4 (s) | GATE | keyword |
| PLAYLOAD |  variable (b) | 0x00-0xFF | payload-bytes |

### MeshCom-Server <--> MeshCom-Reflector

### LOGIN

MeshCom-Server login to MeshCom-Reflector

| Element | type | Format  | Info |
| -------- | ------- |------- |------- |
| TYPE| fixed 5 (s) | LOGN | keyword |
| Server-Callsign |  fixed 9 (s) | "OE1XAR-15" filup | with blank |
| Login-Hash |  variable (s) (0x00) | #1234567890 0x00 | end with hex 0x00|

### CONN

Answer MeshCom-Reflector to MeshCom-Server following a LOGIN-Message

| Element | type | Format  | Info |
| -------- | ------- |------- |------- |
| TYPE| fixed 4 (s) | CONN | keyword |
| separation| fixed 1 (b) | 0x00 | |
| Server-Callsign |  fixed 9 (s) | "OE1XAR-15" filup | with blank |

## Construction type legend

| type | length |  Info |
| -------- | ------- |------- |
| fixed | length |  fixed with #chars defined|
| varable| length |  end with 0x00 |
| (s) | characters |  all chars 'a' ... between 0x01 - 0x7f|
| (9) | numbers |  all numbers between '0'-'9' |
| (x) | hex |  bytes as "00" - "FF" |
| (b) | byte |  bytes as 0x00 - 0xFF |