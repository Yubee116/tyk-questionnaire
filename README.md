

## Question 6

Please follow these steps to delete a key from your redis:

### **Prerequisites:**
- Terminal access to the Redis Container/Cluster
- Keyhash of the key you wish to delete

### **The Process**
1. On the Redis container/cluster terminal, open the Redis CommandLine interface using:

```bash
$ redis-cli
```  
<br>

2. To list the keys in the Resis data store, use the `KEYS` command followed by a specific pattern.    
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
The number of keys that were removed is returned; 1 in this case
