---
description: aws Athena
---

# Athena

## Schema

### Metadata

```sql
SELECT * FROM information_schema.tables where table_schema='information_schema'
```

### List all schema

```sql
SELECT * FROM information_schema.schemata
```

### List all tables in a schema

```sql
SELECT table_name FROM information_schema.tables where table_schema='<db_name>'
```

### Generate Row Count script

```sql
with t(i) as (
	SELECT 'SELECT ''' || table_name || 
		''' as table_name, count(*) as count FROM ' || table_name
	FROM information_schema.tables
	where table_schema = '<db_name>'
)
select array_join(array_agg(i), ' union ' ) as result
from t
```
