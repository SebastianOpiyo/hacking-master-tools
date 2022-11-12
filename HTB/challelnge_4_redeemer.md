1. Which TCP is open
 - Use nmap tool. Example: ```sudo nmap 192.168.0.1```
 - to scan all port & running services ```nmap -p- -sV <IP>```

 2. REDIS DB Details
 - redis runs on port 6379
 - Redis stores data in memory, but depending on your use case, it can copy data on disk; important when you have a large amount of data that you might need to restore
 - Redis regularly dumps is data to an RDB file on disk based on how snapshots are configured. 
 - `redis.config` file contains Redis Configuration
 - Configuration file is located at `/etc/redis/redis.config`
 - Create a snapshot for redis db `$redis-cli SAVE`
 - we can also use `BGSAVE` which works asynchronously
 - Exit cli with `exit`
 - At this stage, the RDB file will be saved in `/var/lib/redis/` and will be named `dump.rdb`.
- Starting and stopping redis server `sudo service redis-server stop` abd `sudo service redis-server start`
- List the number of redis db use any of the following commands `redis-cli INFO keyspace` or to know the number of DBs `CONFIG GET databases`
- Select database with `SELECT index`
- Use `GET key` to get the contents of a key e.g `get flag`