# AWS REDSHIFT
- massively Parallel Processing (MPP) - automatically distributes data/query
loads across all nodes
- easy to add nodes
- RedShift chooses compression scheme based on sampling of data

## Limitations
only available in 1 AZ
Block Size 1MB or 1024KB

## Encryption
SSL in transit
AES-256 at rest

## Key Management
AWS Key Management Service or your own keys through HSM

## Billing
- per hour
- scales from $0.25/hr up to $1,000+ per terabyte per year
- charged for backups
- charged for data transfer within VPC
- not charged for data transfer outside of VPC

### Compute Node Hours
Charged for compute nodes only - not leader nodes
Total # of hours across all nodes
1 unit per node per hour
Ex. 3-node warehouse cluster would incur 2,160 instance hours

## Nodes
### Single Node
160gb

### Leader Node (Multi-Node)
Communicator
manages client connections and receives queries

### Compute Node (Multi-Node)
store data and perform queries/computations
up to 128 compute nodes
