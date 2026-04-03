# CONNECTIONS
## KEEP
The KEEP message initiates the connection of a Node gateway to the MeshCom server.

### Construction

#### KEEP
| Element | type | Format  | Info |
| -------- | ------- |------- |------- |
| TYPE| fixed 4 (s) | KEEP | keyword |
| NODE-HEX-ID | fixed 8 (x) | "F03C1582" | last 4 bytes |
| NODE-Callsign |  fixed 9 (s) | "OE1KBC-12" filup | with blank |
| FW-VERSION |  fixed 4 (s) | 4.35 | |
| FW-SUB-VERSION |  fixed 1 (s) | p | |
| Booked groups |  variable (s) (0x00) | 20;232;262; | separeted by semicolon |

#### BEAT
| Element | type | Format  | Info |
| -------- | ------- |------- |------- |
| TYPE| fixed 4 (s) | BEAT | keyword |
| separation| fixed 1 (b) | 0x00 | |
| GATEWAY-Callsign length |  fixed 1 (b) | 0x00-0xFF | length of following GATEWAY-callsign |
| GATEWAY-Callsign |  variable (s) | "OE1KBC-12" | |

#### DATA
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

#### GATE
| Element | type | Format  | Info |
| -------- | ------- |------- |------- |
| TYPE| fixed 4 (s) | GATE | keyword |
| PLAYLOAD |  variable (b) | 0x00-0xFF | payload-bytes |

#### Construction legend

| type | length |  Info |
| -------- | ------- |------- |
| fixed | length |  fixed with #chars defined|
| varable| length |  end with 0x00 |
| (s) | characters |  all chars 'a' ... between 0x01 - 0x7f|
| (9) | numbers |  all numbers between '0'-'9' |
| (x) | hex |  bytes as "00" - "FF" |
| (b) | byte |  bytes as 0x00 - 0xFF |