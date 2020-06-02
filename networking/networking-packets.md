# NETWORKING - PACKETS
[Great Link]
(https://www.destroyallsoftware.com/compendium/network-protocols?share_key=97d3ba4c24d21147)

## Frame
core of a packet
1,500 byte payload (97% - 1500 of 1542 bytes)
22 bytes for header info like source / dest MAC address, payload length,
checksum
Frame is wrapped in another layer of headers to form full packet

## Minimum Packet payload
1,500 bytes - 20 bytes for minum header
1,480 bytes - 20 bytes for minimum tcp header size
Conservative payload size is 1,400 bytes

## Packet preamble
56 bits (7 bytes), used to sync clocks
8 bit (1 byte) start frame delimiter, number 171 (10101011 in binary)
Frame
interpacket gap of 96 bits (12 bytes) where the line is left idle

## Example Transmit 1500 bytes of data
add 22 bytes to create frame
add 20 bytes of extra data accomodating hardware's needs, creating a full
Ethernet packet

## Analog Range
-2.5 V to +2.5 V
each set of 8 bits gets expanded to 10 bits
256 possible 8-bit values
1024 possible 10-bit values

## Example 8-bit to 10-bit mappping
- Prevents cable from continuously pulling electrons (+2.5 V) which could charge
  up capacitors in low pass filters
- Each 8-bit byte can be mapped to any four different 10-bit patterns, each of
  which will be turned back into the same 8-bit byte on the receiving end
- 10-bit value 00.0000.0000 could map to 8-bit value 0000.0000
- 10-bit value 10.1010.1010 could map to 0000.0000
- When Ethernet device sees 00.0000.0000 or 10.1010.1010 they'll be understood
  as the byte 0 (binary 0000.0000)
