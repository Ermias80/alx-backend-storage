# 0x01. NoSQL
**Back-end NoSQL MongoDB**
This project provides exercises to practice working with the MongoDB NoSQL database.
## RESOURCES
**Read or watch:**
+ [x] [NoSQL Databases Explained](https://intranet.alxswe.com/rltoken/wweK7dOY4pf8haCqv9Iv6Q)
+ [x] [What is NoSQL ?](https://intranet.alxswe.com/rltoken/QqqNmgzgwopHBv305ki6bg)
+ [x] [MongoDB with Python Crash Course - Tutorial for Beginners](https://intranet.alxswe.com/rltoken/RyyP9OH1EMBWWYpTs4TqoA)
+ [x] [MongoDB Tutorial 2 : Insert, Update, Remove, Query](https://intranet.alxswe.com/rltoken/9__3tR-NimgXlmjPQwTF-Q)
+ [x] [Aggregation](https://intranet.alxswe.com/rltoken/ziEDeniRobC6owPE1_avAQ)
+ [x] [Introduction to MongoDB and Python](https://intranet.alxswe.com/rltoken/axwwF4CjO7FnK8Ecochqnw)
+ [x] [mongo Shell Methods](https://intranet.alxswe.com/rltoken/lUqnLwOHbbp9FK39ijNmDQ)
+ [x] [The mongo Shell](https://intranet.alxswe.com/rltoken/bffQMLcTB4cg1bKqgBW3jw)  
## Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:
## General
* What `NoSQL` means
* What is difference between `SQL` and `NoSQL`
* What is `ACID`
* What is a document storage
* What are `NoSQL` types
* What are benefits of a `NoSQL` database
* How to query information from a `NoSQL` database
* How to insert/update/delete information from a `NoSQL` database
* How to use `MongoDB`
## Requirements
### MongoDB Command File
* All your files will be interpreted/compiled on Ubuntu 18.04 LTS using `MongoDB (version 4.2)`
* All your files should end with a new line
* The first line of all your files should be a comment: `// my comment`
* A `README.md` file, at the root of the folder of the project, is mandatory
* The length of your files will be tested using `wc`
### Python Scripts
* All your files will be interpreted/compiled on `Ubuntu 18.04 LTS` using `python3 (version 3.7) and PyMongo (version 3.10)`
* All your files should end with a new line
* The first line of all your files should be exactly `#!/usr/bin/env python3`
* A `README.md` file, at the root of the folder of the project, is mandatory
* Your code should use the `pycodestyle style (version 2.5.*)`
* The length of your files will be tested using `wc`
* All your modules should have a documentation (`python3 -c 'print(__import__("my_module").__doc__)'`)
* All your functions should have a documentation (`python3 -c 'print(__import__("my_module").my_function.__doc__`)'
* Your code should not be executed when imported (by using if `__name__ == "__main__":`)
## More Info
### Install MongoDB 4.2 in Ubuntu 18.04
[Official installation guide](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/ "Official installation guide")
```
$ wget -qO - https://www.mongodb.org/static/pgp/server-4.2.asc | apt-key add -
$ echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.2 multiverse" > /etc/apt/sources.list.d/mongodb-org-4.2.list
$ sudo apt-get update
$ sudo apt-get install -y mongodb-org
...
$  sudo service mongod status
mongod start/running, process 3627
$ mongo --version
MongoDB shell version v4.2.8
git version: 43d25964249164d76d5e04dd6cf38f6111e21f5f
OpenSSL version: OpenSSL 1.1.1  11 Sep 2018
allocator: tcmalloc
modules: none
build environment:
    distmod: ubuntu1804
    distarch: x86_64
    target_arch: x86_64
$  
$ pip3 install pymongo
$ python3
>>> import pymongo
>>> pymongo.__version__
'3.10.1'
```
Potential issue if documents creation doesn’t work or this error: `Data directory /data/db not found., terminating` ([source](https://bryantson.medium.com/fixing-data-db-not-found-error-in-macos-x-when-starting-mongodb-d7b82abb2479 "source") and [source](https://stackoverflow.com/questions/37702957/mongodb-data-db-not-found "source"))
```
$ sudo mkdir -p /data/db
```
Or if `/etc/init.d/mongod` is missing, please find here an example of the file:
Click to expand/hide file contents
### Use “container-on-demand” to run MongoDB
*  Ask for container `Ubuntu 18.04 - MongoDB`
* Connect via `SSH`
* Or via the WebTerminal
* In the container, you should start `MongoDB` before playing with it:
```
$ service mongod start
* Starting database mongod                                              [ OK ]
$
$ cat 0-list_databases | mongo
MongoDB shell version v4.2.8
connecting to: mongodb://127.0.0.1:27017/?compressors=disabled&gssapiServiceName=mongodb
Implicit session: session { "id" : UUID("70f14b38-6d0b-48e1-a9a4-0534bcf15301") }
MongoDB server version: 4.2.8
admin   0.000GB
config  0.000GB
local   0.000GB
bye
$
```
## Tasks
+ [x] 0. **List all databases**<br/>[0-list_databases](0-list_databases) contains a MongoDB script that lists all databases in MongoDB.
+ [x] 1. **Create a database**<br/>[1-use_or_create_database](1-use_or_create_database) contains a MongoDB script that creates or uses the database `my_db`.
+ [x] 2. **Insert document**<br/>[2-insert](2-insert) contains a MongoDB script that inserts a document in the collection `school`:
  + The document must have one attribute `name` with value “Holberton school”.
  + The database name will be passed as an option of `mongo` command.
+ [x] 3. **All documents**<br/>[3-all](3-all) contains a MongoDB script that lists all documents in the collection `school`:
  + The database name will be passed as an option of `mongo` command.
+ [x] 4. **All matches**<br/>[4-match](4-match) contains a MongoDB script that lists all documents with `name="Holberton school"` in the collection `school`:
  + The database name will be passed as an option of `mongo` command.
+ [x] 5. **Count**<br/>[5-count](5-count) contains a MongoDB script that displays the number of documents in the collection `school`:
  + The database name will be passed as an option of `mongo` command.
+ [x] 6. **Update**<br/>[6-update](6-update) contains a MongoDB script that adds a new attribute to a document in the collection `school`:
  + The script should update only document with `name="Holberton school"` (all of them).
  + The update should add the attribute `address` with the value “972 Mission street”.
  + The database name will be passed as an option of `mongo` command.
