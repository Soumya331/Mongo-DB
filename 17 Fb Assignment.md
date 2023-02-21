Ans1) MongoDB is a document database with the scalability and flexibility that you want with the querying and indexing that you need. Non-relational databases are different from traditional relational databases in that they store their data in a non-tabular form. Instead, non-relational databases might be based on data structures like documents. It is popularly used in collaboration with AWS, Azure, and many other data sources for application development and functioning.

Ans2) Features of MongoDB:
Document Oriented: In MongoDB, all the data stored in the documents instead of tables like in RDBMS. In these documents, the data is stored in fields(key-value pair) instead of rows and columns which make the data much more flexible in comparison to RDBMS. And each document contains its unique object id.
High Performance: The performance of MongoDB is very high and data persistence as compared to another database due to its features like scalability, indexing, replication, etc.
Replication: MongoDB provides high availability and redundancy with the help of replication, it creates multiple copies of the data and sends these copies to a different server so that if one server fails, then the data is retrieved from another server.

Ans3)
```python
pip install pymongo
```

    Requirement already satisfied: pymongo in /opt/conda/lib/python3.10/site-packages (4.3.3)
    Requirement already satisfied: dnspython<3.0.0,>=1.16.0 in /opt/conda/lib/python3.10/site-packages (from pymongo) (2.3.0)
    Note: you may need to restart the kernel to use updated packages.



```python
import pymongo
client = pymongo.MongoClient("mongodb+srv://soumyarai:LCg4AGTUohzDfxyN@cluster0.gldmp7t.mongodb.net/?retryWrites=true&w=majority")
db = client.test
```


```python
client
```




    MongoClient(host=['ac-t3pkhoj-shard-00-02.gldmp7t.mongodb.net:27017', 'ac-t3pkhoj-shard-00-00.gldmp7t.mongodb.net:27017', 'ac-t3pkhoj-shard-00-01.gldmp7t.mongodb.net:27017'], document_class=dict, tz_aware=False, connect=True, retrywrites=True, w='majority', authsource='admin', replicaset='atlas-tiiiu6-shard-0', tls=True)




```python
client = pymongo.MongoClient("mongodb+srv://soumyarai:LCg4AGTUohzDfxyN@cluster0.gldmp7t.mongodb.net/?retryWrites=true&w=majority")
```


```python
db = client['Soumya']
```


```python
coll_create = db["my_record"]
```

Ans4)
```python
data = [
  { "name": "Amy", "address": "Apple st 652" },
  { "name": "Hannah", "address": "Mountain 21" },
  { "name": "Michael", "address": "Valley 345" },
  { "name": "Sandy", "address": "Ocean blvd 2" },
  { "name": "Betty", "address": "Green Grass 1" },
  { "name": "Richard", "address": "Sky st 331" },
  { "name": "Susan", "address": "One way 98" },
  { "name": "Vicky", "address": "Yellow Garden 2" },
  { "name": "Ben", "address": "Park Lane 38" },
  { "name": "William", "address": "Central st 954" },
  { "name": "Chuck", "address": "Main Road 989" },
  { "name": "Viola", "address": "Sideway 1633" }
]
```


```python
coll_create.insert_many(data)
```




    <pymongo.results.InsertManyResult at 0x7f74185edf00>




```python
data1 = {
 "name": "notebook",
 "qty": 50,
 "rating": [ { "score": 8 }, { "score": 9 } ],
 "size": { "height": 11, "width": 8.5, "unit": "in" },
 "status": "A",
 "tags": [ "college-ruled", "perforated"]
}
```


```python
coll_create.insert_one(data1)
```




    <pymongo.results.InsertOneResult at 0x7f7418502dd0>




```python
for i in coll_create.find():
    print(i)
```

    {'_id': ObjectId('63f470c7401e50855c88e887'), 'name': 'Amy', 'address': 'Apple st 652'}
    {'_id': ObjectId('63f470c7401e50855c88e888'), 'name': 'Hannah', 'address': 'Mountain 21'}
    {'_id': ObjectId('63f470c7401e50855c88e889'), 'name': 'Michael', 'address': 'Valley 345'}
    {'_id': ObjectId('63f470c7401e50855c88e88a'), 'name': 'Sandy', 'address': 'Ocean blvd 2'}
    {'_id': ObjectId('63f470c7401e50855c88e88b'), 'name': 'Betty', 'address': 'Green Grass 1'}
    {'_id': ObjectId('63f470c7401e50855c88e88c'), 'name': 'Richard', 'address': 'Sky st 331'}
    {'_id': ObjectId('63f470c7401e50855c88e88d'), 'name': 'Susan', 'address': 'One way 98'}
    {'_id': ObjectId('63f470c7401e50855c88e88e'), 'name': 'Vicky', 'address': 'Yellow Garden 2'}
    {'_id': ObjectId('63f470c7401e50855c88e88f'), 'name': 'Ben', 'address': 'Park Lane 38'}
    {'_id': ObjectId('63f470c7401e50855c88e890'), 'name': 'William', 'address': 'Central st 954'}
    {'_id': ObjectId('63f470c7401e50855c88e891'), 'name': 'Chuck', 'address': 'Main Road 989'}
    {'_id': ObjectId('63f470c7401e50855c88e892'), 'name': 'Viola', 'address': 'Sideway 1633'}
    {'_id': ObjectId('63f4729a401e50855c88e893'), 'name': 'notebook', 'qty': 50, 'rating': [{'score': 8}, {'score': 9}], 'size': {'height': 11, 'width': 8.5, 'unit': 'in'}, 'status': 'A', 'tags': ['college-ruled', 'perforated']}
    {'_id': ObjectId('63f47697401e50855c88e896'), 'name': 'Amy', 'address': 'Apple st 652'}
    {'_id': ObjectId('63f47697401e50855c88e897'), 'name': 'Hannah', 'address': 'Mountain 21'}
    {'_id': ObjectId('63f47697401e50855c88e898'), 'name': 'Michael', 'address': 'Valley 345'}
    {'_id': ObjectId('63f47697401e50855c88e899'), 'name': 'Sandy', 'address': 'Ocean blvd 2'}
    {'_id': ObjectId('63f47697401e50855c88e89a'), 'name': 'Betty', 'address': 'Green Grass 1'}
    {'_id': ObjectId('63f47697401e50855c88e89b'), 'name': 'Richard', 'address': 'Sky st 331'}
    {'_id': ObjectId('63f47697401e50855c88e89c'), 'name': 'Susan', 'address': 'One way 98'}
    {'_id': ObjectId('63f47697401e50855c88e89d'), 'name': 'Vicky', 'address': 'Yellow Garden 2'}
    {'_id': ObjectId('63f47697401e50855c88e89e'), 'name': 'Ben', 'address': 'Park Lane 38'}
    {'_id': ObjectId('63f47697401e50855c88e89f'), 'name': 'William', 'address': 'Central st 954'}
    {'_id': ObjectId('63f47697401e50855c88e8a0'), 'name': 'Chuck', 'address': 'Main Road 989'}
    {'_id': ObjectId('63f47697401e50855c88e8a1'), 'name': 'Viola', 'address': 'Sideway 1633'}
    {'_id': ObjectId('63f47698401e50855c88e8a2'), 'name': 'notebook', 'qty': 50, 'rating': [{'score': 8}, {'score': 9}], 'size': {'height': 11, 'width': 8.5, 'unit': 'in'}, 'status': 'A', 'tags': ['college-ruled', 'perforated']}



```python
coll_create.find_one()
```




    {'_id': ObjectId('63f470c7401e50855c88e887'),
     'name': 'Amy',
     'address': 'Apple st 652'}



Ans5) In mongoDB, the find() method is used to fetch a particular data from the table. In other words, it is used to select data in a table.


```python
for i in coll_create.find({'name': 'Chuck'}):
    print(i)
```

    {'_id': ObjectId('63f470c7401e50855c88e891'), 'name': 'Chuck', 'address': 'Main Road 989'}
    {'_id': ObjectId('63f47697401e50855c88e8a0'), 'name': 'Chuck', 'address': 'Main Road 989'}


Ans6) For sorting your MongoDB documents, you need to make use of the sort() method. This method will accept a document that has a list of fields and the order for sorting. For indicating the sorting order, you have to set the value 1 or -1 with the specific entity based on which the ordering will be set and displayed. One indicates organizing data in ascending order while -1 indicates organizing in descending order.
Eg: db.coll_create.find().sort({'name': 1})

Ans7) delete_one() - To delete one document, we use the delete_one() method.The first parameter of the delete_one() method is a query object defining which document to delete.
delete_many() - To delete more than one document, use the delete_many() method.The first parameter of the delete_many() method is a query object defining which documents to delete.
drop() - We can delete a table, or collection as it is called in MongoDB, by using the drop() method. The drop() method returns true if the collection was dropped successfully, and false if the collection does not exist.

