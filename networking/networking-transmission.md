# NETWORKING - TRANSMISSION

## ACK
Acknowledgement
ACKing the most recent packet implicitly ACKs all earlier ones

## TCP Fast Retransmit
Sender sees 3 dupe ACKs in a row, assumes following packet was lost and
retransmits it

## Out of Order Packets
Any out of order packet causes receiver to re-ACK the last 'good packet'
Duplicate ACKS can get sent until the sender sends the missing packet to the
receiver

## Congestion Window
In linux kernel, const `TCP_INIT_CWND`
Slow start is small congestion windows like 14KB
Sender and receiver have congestion windows and get adjusted by ACKs
Lost packets trigger a reduction in the congestion window size

## Packet Tracking
TCP uses simple mechanism: a counter (sequence number)

## Border Gateway Protocol
Repsonsible for communicating routing table information between routers
