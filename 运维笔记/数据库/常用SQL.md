## 常用SQL

标签: #MySQL

### 只读用户创建

```
create user baas_read@'%' identified by 'Lv7Hd39Gol90';
grant select on *.* to baas_read@'%';   
```

### 统计空间

```
# 表占用
select concat(round(sum(data_length/1024/1024),2),'MB') as data_length_MB,  
     concat(round(sum(index_length/1024/1024),2),'MB') as index_length_MB  
     from information_schema.tables 
     where table_schema='库名' and table_name = '表名'; 
```