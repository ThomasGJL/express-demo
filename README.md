# express-demo
  
安装Express框架

```
npm install -g express-generator
```
  
创建应用

```
express express-demo
```
  
安装所需的模块

```
npm install
```

Docker 部署 postgres
    
```
docker pull postgres:14.2
```
  
```
docker run --name postgres-db -e POSTGRES_DB=database -e POSTGRES_PASSWORD=your password -e PGDATA=/var/lib/postgresql/data -p 5432:5432 -d postgres:14.2
```
  
```
docker logs postgres-db 
```
  
```
docker exec -it postgres-db /bin/bash
```
  
Postgres主键自增
  
先创建SEQUENCE
```
CREATE SEQUENCE table_id_seq
START WITH 1
INCREMENT BY 1
NO MINVALUE
NO MAXVALUE
CACHE 1;
```

主键加默认
```
nextval('table_id_seq'::regclass)
```
