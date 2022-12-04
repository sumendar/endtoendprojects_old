```python
## Using SQLite With Python
```

<iframe src="https://assets.pinterest.com/ext/embed.html?id=420523683962989537" height="445" width="345" frameborder="0" scrolling="no" ></iframe>

**Link:**  
https://subscription.packtpub.com/video/application-development/9781838982867/116872/116877/query-and-fetchall


```python
    import sqlite3
```

## Using SQLite With Python

### Create SQLite Connection


```python
#%%sql
#conn = sqlite3.connect(
#    ":memory:"
#)  #store database inmemory temporary without perminent(placed inmemory like Ram  it will delete )
```


```python
conn = sqlite3.connect("customer.db")
```

### Create A Database Table  
**`SQLite is Case Sensitive`  
(*Lowercase shoule be in lower and Uppercase should be in uppercase*)**


```python
c = conn.cursor() # cursor to pointout 
```


```python
# create a table
c.execute("""CREATE TABLE customers (
                first_name DATATYPE,
                last_name DATATYPE,
                email DATATYPE)
                """)
```


```python
c.execute("DROP TABLE customers")
```




    <sqlite3.Cursor at 0x13cc6b19650>




```python
# create a table
c.execute("""CREATE TABLE customers (
                first_name text,
                last_name text,
                email text)
                """)
```




    <sqlite3.Cursor at 0x13cc6b19650>



###  Commit the Connection


```python
conn.commit() # commit the execution
```

### Close the Connection


```python
conn.close() # close the connection
```

### ReConnect with the database we want and execute the queries  
`Closed coonnection will not execute,   so we have to  connect again and create the cursor for execution`


```python
conn = sqlite3.connect("customer.db")
```


```python
c = conn.cursor() # cursor to pointout 
```


```python
c.execute("INSERT INTO customers VALUES('John', 'Eler', 'john@codemy.com')")
```




    <sqlite3.Cursor at 0x13cc6b2a880>




```python
c.execute("SELECT * FROM customers")
# this would be run with the above line so get the output (indivisual this line run will not get output)
print(c.fetchone())
```

    ('John', 'Eler', 'john@codemy.com')
    
