```
cat /data/oracle/oracle/product/11.2.0/db_1/network/admin/listener.ora

LISTENER =
  (DESCRIPTION_LIST =
    (DESCRIPTION =
      (ADDRESS = (PROTOCOL = IPC)(KEY = EXTPROC1521))
      (ADDRESS = (PROTOCOL = TCP)(HOST = 修改为具体IP)(PORT = 1521))
    )
  )

ADR_BASE_LISTENER = /data/oracle/oracle

LOGGING_LISTENER=OFF
```
