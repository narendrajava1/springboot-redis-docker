# springboot-redis-docker
redis-what-and-why-springoot-docker

Since last few days at work, my seniors suddenly started worrying about the cost of AWS as the users for our product started increasing rapidly, which means large audience interaction, large database requests, large response time, and obviously large costs. It was really strange for me to understand the whole situation because of my very less experience in the IT industry to know how could we actually save the god damn database requests? As far as I knew saving data could be done via database only.

I was wrong..

After an hour of discussion about how we can actually save the number of requests to the database, we finally decided to do something known as Caching.

So..

What is Caching?
Caching is the process of storing some data in Cache. Cache is a temporary storage component area where the data is stored so that in future, Data can be served faster.
For our case, we decided to go with Redis.

What is Redis?
According to Redis homepage, Redis is an open source (BSD licensed), in-memory data structure store, used as a database, cache and message broker.
It supports various data structures such as Strings, Hashes, Lists, Sets etc.

Why use Redis?
1.It is blazingly fast! After all, it has been written in C.
2. It’s a NoSql Database. That’s Amazingly amazing!
3. Currently, it is being used by tech-giants like GitHub,Weibo, Pinterest, Snapchat, Craigslist, Digg, StackOverflow, Flickr.
4. In order to save your cloud database calls and eventually saving some dollars out there, you can of course opt for caching so the Redis.

5. It is Developer friendly and by that I mean to say that Redis is being supported in most of the languages (Perks of using an Open Source Technology). Languages like JavaScript, Java, Go, C, C++, C#, Python, Objective-C, PHP and almost every famous language out there has support for this.

6. Last and probably the very obvious point, it is open source and stable, so yeah that’s another thing to say ‘Yes’ to Redis.

Sample Redis Commands
Although Redis comes with written documentation, but in order to give idea to the audience, I am presenting few over here. I am using Redis-CLI for the demonstration. By Default, Redis-CLI runs on port 6379.

SET (Setting a Key)
127.0.0.1:6379> SET foo "Hello World"
OK // setting a key
GET (Getting a Key)
127.0.0.1:6379> GET foo
"Hello World" // getting a key
DEL (Deleting a Key)
127.0.0.1:6379> GET foo 
"Hello World" // getting a key
127.0.0.1:6379> DEL foo
(integer) 1 // key just got deleted
127.0.0.1:6379> GET foo
(nil) // since key is deleted therefore, result is nil.
SETEX (Setting a key with an expiry)
127.0.0.1:6379> SETEX foo 40 "I said, Hello World!"
OK // key has been set with 40 seconds as expiration
TTL (Total Time left for a key that has a timeout)
127.0.0.1:6379> TTL foo
(integer) 36 // 36 seconds left to timeout
PERSIST (Removing the timeout from key)
127.0.0.1:6379> PERSIST foo
(integer) 1 // turning the key from volatile to persistent (key won't expire)
RENAME (Renaming the current existing key)
127.0.0.1:6379> RENAME foo bar
OK // renaming the key 'foo' as bar
FLUSHALL (Flushing everything so far saved)
127.0.0.1:6379> flushall
OK // just got flushed
So that was just the introductory part of what you can do with Redis. Redis is extremely powerful and even I am also using on daily basis for faster performance of data being transmitted between the applications.
In short, Redis is cool.

