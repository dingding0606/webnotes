# sqlite3 - Python

在flask框架中，`.db	`文件应该和`app.py`放在一个目录下。



###Python sqlite3 模块 API



**sqlite3.connect(database [,timeout ,other optional arguments])**

该 API 打开一个到 SQLite 数据库文件 database 的链接。

如果给定的数据库名称 filename 不存在，则该调用将创建一个数据库。如果您不想在当前目录中创建数据库，那么您可以指定带有路径的文件名，这样您就能在任意地方创建数据库。

返回一个`connection`	对象



**connection.cursor([cursorClass])**

返回一个`cursor`	对象



**cursor.execute(sql [, optional parameters])**

执行一个 SQL 语句。



**connection.commit()**

该方法提交当前的事务。如果您未调用该方法，那么自您上一次调用 commit() 以来所做的任何动作对其他数据库连接来说是不可见的。



```python
In [1]: import sqlite3

In [3]: conn = sqlite3.connect('/Users/dingding/Desktop/workspace/finance/finance.db')

In [4]: conn
Out[4]: <sqlite3.Connection at 0x105f44810>

In [5]: db = conn.cursor()

In [6]: db
Out[6]: <sqlite3.Cursor at 0x1060158f0>

In [15]: result = db.execute("SELECT symbol, SUM(shares) FROM history WHERE userid=? GROUP BY symbol", (1,))

In [16]: for data in result:
    ...:     print(data, "\n")
    ...:     
('AMZN', 2) 

('GOOG', 5) 

('TCNT', 20) 

('X', 10) 
```

