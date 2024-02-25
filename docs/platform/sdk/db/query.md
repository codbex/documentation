# Query

# Overview

The provided TypeScript module `Query` facilitates the execution of SQL queries in a database. It includes a method for executing queries. Here's an explanation of the key components:

## QueryParameter Interface:

```javascript
export interface QueryParameter {
	readonly type: string;
	readonly value: any;
}
```

This interface represents a parameter that can be used in an SQL query. It includes the `type` of the parameter (string) and its `value` (any).

## Query Class:

The `Query` class provides a static method for executing SQL queries.

### execute

```javascript
execute(sql: string, parameters?: (string | number | boolean | Date | QueryParameter)[], datasourceName?: string): any[]
```

Executes an SQL query and returns the result sets.

**Parameters:**

* `sql`: The SQL statement to be executed.
* `parameters`: (Optional) An array of parameters to be included in the SQL query. Parameters can be of type string, number, boolean, Date, or an object conforming to the QueryParameter interface.
* `datasourceName`: (Optional) The name of the data source.
* Return Value: An array containing the result sets of the SQL query execution.

## Example Usage:

```javascript
import { Query, QueryParameter } from 'sdk/db/query';

// Example SQL query
const sql = 'SELECT * FROM your_table WHERE column1 = ? AND column2 > ?';

// Example parameters
const parameters: (string | number | boolean | Date | QueryParameter)[] = [
  'value1',
  42,
  true,
  new Date('2024-02-28'),
  { type: 'custom', value: 'custom value' } as QueryParameter
];

// Execute the SQL query
const result = Query.execute(sql, parameters, 'yourDataSource');

console.log('Query Result:', result);
```

Replace `your_table`, `column1`, `column2`, `value1`, `42`, `true`, `2024-02-28`, `custom value`, `yourDataSource`, and other placeholders with your actual module path, table name, column names, values, data source, and query details.