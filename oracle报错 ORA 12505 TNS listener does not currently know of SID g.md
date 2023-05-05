oracle报错：ORA-12505, TNS:listener does not currently know of SID given in connect descriptor
 
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



app服务器 ： jq命令

