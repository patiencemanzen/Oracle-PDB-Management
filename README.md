# Oracle-PDB-Management

### Create PDB in Oracle
This query is used to create a pluggable database named ```oracle-PDB-management```
```sql
  -- create the pdb
  CREATE PLUGGABLE DATABASE oracle-PDB-management ADMIN USER admin IDENTIFIED BY admin ROLES=(DBA);
  ALTER PLUGGABLE DATABASE oracle-PDB-management OPEN READ WRITE FORCE;
   
  -- grant privileges
  ALTER SESSION SET CONTAINER = oracle-PDB-management;
  GRANT CREATE SESSION TO admin CONTAINER=CURRENT;
  GRANT SYSDBA TO admin CONTAINER=CURRENT;
```

### Delete PDB in Oracle
```sql
-- close first the pdb to kill any active sessions
ALTER PLUGGABLE DATABASE oracle-PDB-management CLOSE IMMEDIATE; 
DROP PLUGGABLE DATABASE oracle-PDB-management INCLUDING DATAFILES;
```
