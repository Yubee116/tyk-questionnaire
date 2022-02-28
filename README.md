

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
Exit the Redis CLI and the terminal using `exit`
<br>
<br>

## Question 7 (Delete User through Dashboard API using Curl)

Curl command to delete a user, as run on my local machine:
```bash
$ curl -i -H "Authorization: 1c529b45dceb4283407313ee9ff5c079" -X DELETE http://localhost:3000/api/users/<user-id>
```
The Authorization is your Dashboard API Access Credentials  
![image](https://user-images.githubusercontent.com/49939534/155908365-cc05c6f9-8eed-448d-bdc8-d72b9dc947a1.png)

<br>
<br>

## Question 7 (Delete User in MongoDB)

Please follow these steps to delete a user from your MongoDB:

### **Prerequisites:**
- Existing Tyk configured to use MongoDB
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
Exit the Mongo CLI and the terminal using `exit`
<br>
<br>

## Question 8

Curl command to retrieve activity data of all endpoints called using the key 7f3c3ca87376cabe between February 10th 2020 and February 18th 2022, as run on my local machine:
```bash
$ curl -i -H "Authorization: 1c529b45dceb4283407313ee9ff5c079" http://localhost:3000/api/activity/keys/endpoint/7f3c3ca87376cabe/10/2/2022/18/2/2022
```
The Authorization is your Dashboard API Access Credentials  
![image](https://user-images.githubusercontent.com/49939534/155908365-cc05c6f9-8eed-448d-bdc8-d72b9dc947a1.png)

