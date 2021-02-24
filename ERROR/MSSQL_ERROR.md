# mssql drop fail

- DB 삭제시 error

```
Drop failed for Database 'YJ' (Microsoft.SqlServer.Smo)

Additional information:

An exception occurred while executing a Transact-SQL statement or batch.
(Microsoft.SqlServer.ConnectionInfo)

데이터베이스 'YJ'은 현재 사용중 이므로 삭제할 수 없습니다.

```
```sql

USE master 
GO 
ALTER DATABASE YJ
SET OFFLINE WITH ROLLBACK IMMEDIATE 
GO

```
