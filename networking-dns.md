# NETWORKING DNS

## Top Level Domains
Controlled by IANA in a root zone database http://www.iana.org/domains/root/db
.com
.edu
.gov
etc

## Domain Names
Domain registrars assign domain names directly under one or more top-level
domains. Registered with InterNIC, a service of ICANN to enforce uniqueness
Central database is WhoIS

## Second Level Domain Name
co.uk
gov.uk
.com.au

## DNS Records are Cached
Depends how long based on TTL value

## Address (A) Record
This is the most important record, resolvers see this record. Used to translate
human readable name to specific ip address

## Alias Records - AWS Route53
NOT visible to resolvers
used to map resource record sets in your hosted zone to ELBs, CloudFront
distributions, or S3 buckets

## Time to Live (TTL)
always measured in seconds

## Canonical Name (CNAME) Record
resolves one domain name to another domain name
ex www.acloud.guru resolves to acloud.guru

## Name Server (NS) Record
Used by top level domain servers to direct traffic to the Content DNS server
which contains the authoritative DNS records

## MX Record
Mail Record

## PTR Record

## Start of Authority (SOA) Record
DNS zone always starts with a single SOA Record
SOA Stores:
- Name of Server
- Administrator
- Current version of file
- Number of seconds to wait for secondary name server to check for updates
- Number of seconds to wait for secondary name server to retry a failed zone
  transfer
- Max number of seconds that secondary name server can use data before it must
  be refreshed or expired
- Default number of seconds for TTL file on resource records

## Root Servers
13 Root servers exist around the world
Managed by ICANN (US based company)

## Resolving DNS Server
Saves authoritative record locally per TTL so it can cache instead of query

## Example DNS flow
User Browser queries Resolving DNS Server
Resolving DNS Server queries Root DNS Server
Resolving DNS Server queries TLD Servers
Resolving DNS Server queries Content DNS Server
Resolving DNS Server returns IP address to User Browser
