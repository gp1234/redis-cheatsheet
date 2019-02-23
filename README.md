# Redis
![Redis](https://d1q6f0aelx0por.cloudfront.net/product-logos/89e5782a-76ea-4b94-a561-39e331c281a5-redis.png)


## Basics
### Strings
* `SET foo 100` to set a key value pair
  * You can set values as `SET server:name someserver` and get it with `GET server:name`
* `GET foo` will return **100**
* `INCR foo` -> to increment a value
* `EXISTS foo ` -> Determines if the key exits
  * It will return _1_ if the value exists otherwise will return 0
*  `DEL foo` -> to delete a value
*  `FLUSHALL` -> to erease everything
*  `EXPIRE foo 50` -> to give an expiration time to our values
*  `TTL foo` -> to see how long this value has
*  `SETEX foo 40 "Hello world" ` to set the value and the expiration at the same time
*  `PERSIST foo` -> to cancel the expiration time.
*  `MSET key1 "Hello1" key2 "World"` -> to set multiple values at the same time
*  `APEND key1 "World"` -> Append 
*  `RENAME key1 greeting` -> to change the key name 

## Lists
* `LPUSH people "Giovanni"` -> to push a name to the people's list
* `LRANGE people 0 -1` -> to output all the values in the list (0 to -1 indecates all the range) **Lists are 0 base**
* `RPUSH people "Jenny" ` to push a value to the end of the list. 
* `LLEN people` -> Gives the lists length
* `LPOP people` -> Eliminate the first element of the list
* `RPOP people` -> Eliminate the last element of the list
* `LINSERT people BEFORE "Jenny" "May"` -> Will insert *before* a certain element. 

## SETS
> Is an unorder collection of strings
* `SADD cars "FORD"` -> to add to the set
* `SISNUMBER cars "FORD"` -> will determinate if it exists.
  * If return _1_ the value exists in the set otherwise returns 0
* `SMEMBERS cars` -> return all members of the set. 
* `SCARD cars` -> Gives how many elements
* `SMOVE cars mycars "Ford"` to move an element to another set.
* `SREM cars "Ford` -> is to remove an element of the set.

## Source Sets
> The difference between source sets and sets is that every memeber of the sorce set is associated with a score
* `ZADD users 1980 "Giovanni" ` -> To Add an element to the source set _1980_ will be its score
* `ZRANK users "Giovani" ` -> To know it which position is that score
* `ZRANGE users 0 -1 ` -> Print all the source set
* `ZINCRBY user 1 "Giovanni"` -> Will return 1981 to the score

## Hashes
* `HSET user:gp1234 name "Giovanni" `
* `HSET user:gp1234 email "giovanni@gmail.com"`
* `HGET user:gp1234 name`
* `HGETALL user:gp1234` -> To return all the values
* `HMSET user:gp1234 name "Giovanni" email "giovanni@gmail.com" age: "24"` -> To set multiple values at the same time.
* `HKEYS user:gp1234` -> to get all the keys
* `HVALS user:gp1234` -> to get just the values
* `HINCRBY user:gp1234 age 1` -> to increment a value
* `HDEL user:gp1234 age` -> to delete a key-value pair
* `HHLEN user:gp1234` -> to get the number of key-value pairs

## Data Persistence

* `SAVE` -> will create a snapshot of our values
*  `SAVE 60 1000` -> every 60 seconds save if a 1000 of items have change
*  You can set `appendonly yes` in the redis configuration file and it will log everything

## Links
[Great free crash course](https://www.youtube.com/watch?v=Hbt56gFj998&t=1530s)
