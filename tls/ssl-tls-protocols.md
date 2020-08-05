# SSL TLS PROTOCOLS

## Protocol Steps
1. Starts with a handshake phase that includes authentication and key exchange
2. Follows with the data exchange phase with confidentiality and integrity
3. Ends with a shutdown sequence

## Protocol Failures
Protocols have much larger attack surface due to complexity

Rules to follow:
1. Use well-established protocols and never design your own schemes
2. Use high-level libraries and never write code that deals with cryptography directly
3. Use well-established primitives with sufficiently strong key sizes

## Sub Protocols
4 core sub protocols

### Handshake Protocol
About 6-10 messages depending on features

3 common flows
- Full handshake with server auth
- Abbreviated handshake that resumes earlier session
- Handshake with client and server auth

### Change Cipher Spec Protocol

### Application data protocol

### Alert protocol
