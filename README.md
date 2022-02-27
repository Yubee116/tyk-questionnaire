

## Question 6

Please follow these steps to delete a key from your Redis:

### **Prerequisites:**
- Terminal access to the Redis Container/Cluster
- Keyhash of the key you wish to delete

### **The Process**
1. On the Redis container/cluster terminal, open the Redis CommandLine interface using:

```bash
$ redis-cli
```  
<br>

2. To list the keys in the Redis data store, use the `KEYS` command followed by a specific pattern.    
Use `*` to match all the keys in the datastore  
Use `apikey-*` to match only Tyk API keys in the datastore 

```bash
$ KEYS *  # list all keys in data store

$ KEYS apikey-* # list apikeys
```
<br>

3. To delete a specific key, use the `DEL` command followed by the name of the key you wish to remove.  
In this case, the name of the key is "apikey-{keyHash}", where {keyHash} is the actual hash of your API key

```bash
$ DEL apikey-{keyHash}
```
<br>
<br>

## Question 7

Please follow these steps to delete a user from your MongoDB:

### **Prerequisites:**
- Terminal access to the MongoDB Container/Cluster
- Emailaddress of the user you wish to delete

### **The Process**
1. On the MongoDB container/cluster terminal, open the MongoDB CommandLine interface using:

```bash
$ mongo
```  
<br>

2. List the available databases, using:      

```bash
> show dbs
```
<br>

3. The 'tyk_analytics' database contains users. Switch to this database using:
```bash
> use tyk_analytics
```
<br>

4. List the collections in the tyk_analytics database using:  
```bash
> show collections
```
<br>

5. Users are located in <tyk_analytics_users> collection.  
User emails are unique in the database collection. Find the user by their email using:
```bash
> db.tyk_analytics_users.find({})  #show all users in the collection

> db.tyk_analytics_users.find({"emailaddress": "userEmail@gmail.com"})  #show specific user by email
```
<br>

6. Delete the user using:  
```bash
> db.tyk_analytics_users.remove({"emailaddress": "userEmail@gmail.com"})
```
