# NORMALIZATION

## Why (Old style reasons)
Cost - no data duplication = cheaper storage
Speed - less data = faster processing
Integrity - no data duplication = integrity
Faster Manipulation - update data once, cascade to all related records

## Downsides
Takes more time and effort
Generates more tables, more relationships, more processing
Queries become complex

## 1st Normal Form (1NF)
Primary key - each row can be identified uniquely
No duplicate rows
No attributes which contain more than one item of information
(debateable - think addresses)

## 2nd Normal Form (2NF)
### 1st Normal tables with only one primary key are in 2nd Normal Form
Data already in 1NF
No partial dependencies on a composite key (Only one row is needed)

Ex. Description/Color/Price are dependent on each other - not 2NF

## 3rd Normal Form (3NF)
No dependencies on non-key attributes
