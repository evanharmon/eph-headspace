# NETWORKING - TCP

# Process TCP Server
Steps:
- Create a socket with socket()
- Bind socket to address with bind()
- Listen for connections with listen()
- Accept connections with accept() "typicall blocks until client connects"
- Send / Receive data with read(), write()

# Process TCP Client
Steps:
- Create a socket with socket()
- Connect to address with connect()
- Send / Receive data with read(), write()
