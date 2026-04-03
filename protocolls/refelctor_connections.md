# CONNECTION
## KEEP
The KEEP message initiates the connection of a gateway to the MshCom reflector.

### Construction

| Element | type | Format  | Info |
| -------- | ------- |------- |------- |
| TYPE| fixed 4 (s) | KEEP | keyword |
| NODE-HEX-ID | fixed 8 (x) | F03C1582 | last 4 bytes |
| NODE-Callsign |  fixed 9 (s) | OE1KBC-12 filup | with blank |
| FW-VERSION |  fixed 4 (s) | 4.35 | |
| FW-SUB-VERSION |  fixed 1 (s) | p | |
| Booked groups |  variable (s) (0x00) | 20;232;262; | separeted by semicolon |

#### Construction legend

| type | length |  Info |
| -------- | ------- |------- |
| fixed | length |  fixed with #chars defined|
| varable| length |  end with 0x00 |
| (s) | characters |  all chars between 0x01 - 0x7f |
| (x) | hex |  bytes as 0x00 - 0xFF |
