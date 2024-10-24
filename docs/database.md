<h1 align="center"><u>PysonDB</u></h1>

* [Install](https://github.com/pysonDB/pysonDB#install) 
* [Example Code](https://github.com/pysonDB/pysonDB/tree/master/example) 
* [Command Line Operations](https://pysondb.github.io/pysonDB/cli) 
* [Database](https://pysondb.github.io/pysonDB/database) 
* [Adding Data](https://pysondb.github.io/pysonDB/add) 
* [Get data](https://pysondb.github.io/pysonDB/get) 
* [Search data](https://pysondb.github.io/pysonDB/re_search) 
* [Update Data](https://pysondb.github.io/pysonDB/update) 
* [Delete Data](https://pysondb.github.io/pysonDB/delete)

<h2>Database Instance</h2>


**Methods**:
  * getDb()
  * **Parameters**:
    * id_fieldname (Defaults to 'id')
    * log (Defaults to False)


<h2><code>getDb(filename)</code></h2>


* You can create a database instance just with filename or file path

```Python
>> import pysondb
>> a = pysondb.getDb('database.json')
```

By default, no logs will be generated, and the id field will be set to 'id'. If you provide some data with **your** id. it will be replaced

Example:

```Python
>> import pysondb
>> a = pysondb.getDb('database.json')
>> new_data = {"id":10, "path":"value"}
>> a.add(new_data)
```

When you open your database.json, you'll see something like this:

```json
{
   "data": [
      {
         "id": 900835764528540182,
         "path": "value"
      }
   ]
}
```

In this case, the **id** value was replaced.

<h2><code>getDb(filename, id_fieldname, log)</code></h2>

* Initialize database with filename and id_fieldname

* ``id_fieldname`` is a random and unique id generated by Pysondb. **Defaults to 'id'**

* Set ``log`` to True if you want to see debug logs. **Defaults to False**


```Python
>> import pysondb
>> a = pysondb.getDb('database.json', id_fieldname='fid',log=True)
Database Filename: database.json
>> new_data = {"id":10,"value":"path"}
>> a.add(new_data)
Add first data entry; {'id': 10, 'value': 'path', 'fid': 342414262596544617}
342414262596544617
```

As you can see, the 'id' field is not replaced, a 'fid' field is created with a system-generated random and unique value.



----

* See full examples [here](https://github.com/pysonDB/pysonDB/example).
* If You have any queries or doubts join the discord server [here](https://discord.gg/SZyk2dCgwg)
