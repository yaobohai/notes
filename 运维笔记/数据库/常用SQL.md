## 常用SQL

标签: #MySQL

### 只读用户创建

```
create user baas_read@'%' identified by 'Lv7Hd39Gol90';
grant select on *.* to baas_read@'%';   
```