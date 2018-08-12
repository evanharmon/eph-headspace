# MYSQL - TROUBLESHOOTING

## Check For Locks
`$ show engine innodb status;`

## Locking Issues
```
SELECT @@GLOBAL.tx_isolation, @@tx_isolation;
SET @@GLOBAL.tx_isolation = "READ-COMMITTED";
SET TX_ISOLATION = "READ-COMMITTED";
```
