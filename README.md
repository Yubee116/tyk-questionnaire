

## Question 6
To open the Redis CommandLine interface:

```bash
$ redis-cli
```
If your Redis cluster is hosted on the local machine, you should automatically drop into the Redis CLI tool as:
```bash
127.0.0.1:6379>
```


To list the keys in the Resis data store, use the `KEYS` command followed by a specific pattern. Redis will search the keys for all the keys matching the specified pattern.
Use `*` to match all the keys in the datastore
Use `apikey-*` to match only Tyk API keys would

```bash
$ KEYS *  # list all keys in data store

$ KEYS apikey-* # list apikeys
```

To delete specific API key, use the `DEL` command followed by the name of the key you wish to remove:
The number of keys that were removed is returned; 1 in this case

```bash
$ DEL apikey-{keyHash}
(integer) 1
```
