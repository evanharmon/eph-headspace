# DOMAIN DRIVEN DESIGN
(http://manuel.kiessling.net/2012/09/28/applying-the-clean-architecture-to-go-applications/)
(https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html)

## Diagram

### Infrastructure
application-agnostic
business-agnostic

### Interfaces
application-specific
business-agnostic

### Use Cases
application-specific
business-specific

### Domain
application-agnostic
business-specific

## Interfaces
main task is to simply transport and translate data between layers

## Injection
used to handle dependencies

## Persistence
Belongs in interfaces layer, repositories are an interface between the low
level world of databases and the high level world of business

Bytes on a hard drive on one side must become an entity object on the other
repository handles the transform

## Persistence Scope
Get data from this table, put data into that table
low level / physical aspects are outside it's scope

## Infrastructure Scope
connecting to database daemon through the network
handling timeouts
