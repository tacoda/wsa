# SQL Injection

> https://portswigger.net/web-security/sql-injection

## SQL injection vulnerability in WHERE clause allowing retrieval of hidden data

When the user selects a category, the application carries out an SQL query like the following:

```sql
SELECT * FROM products WHERE category = 'Gifts' AND released = 1
```

1. Use Burp Suite to intercept and modify the request that sets the product category filter.
2. Modify the category parameter, giving it the value `'+OR+1=1--`
3. Submit the request, and verify that the response now contains additional items.

## SQL injection vulnerability allowing login bypass

Perform an SQL injection attack that logs in to the application as the `administrator` user.

1. Use Burp Suite to intercept and modify the login request.
2. Modify the username parameter, giving it the value: `administrator'--`
