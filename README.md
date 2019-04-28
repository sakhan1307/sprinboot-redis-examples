# sprinboot-redis-examples
sprinboot-redis-examples

1. install Redis on machine
 1.1 On Unix :
 			- download .gz file from https://redis.io/download and extract it.
 			- Download, extract and compile Redis with:
				$ wget http://download.redis.io/releases/redis-5.0.4.tar.gz
				$ tar xzf redis-5.0.4.tar.gz
				$ cd redis-5.0.4
				$ make
			- Run Redis with
				$ src/redis-server
			- You can interact with Redis using the built-in client:
				$ src/redis-cli
 1.2 On windows :
 			- download .zip file or .msi file latest release version from https://github.com/MicrosoftArchive/redis/releases
 			- .msi directly install and run from services
 			- extract .zip file and run the server as below form cmd prompt.
 				cmd> redis-server.exe
 			- You can interact with Redis using the built-in client:
 				cmd> redis-cli.exe
2. Refer https://redis.io/commands/get for cli commands

3. Run Application.java and hit the below urls-
	http://localhost:8090/1
	http://localhost:8090/1
	http://localhost:8090/2
	http://localhost:8090/2
	
  You observe the logs it will shows as below -
	com.example.UserController               : Getting user with ID 1.
	com.example.UserController               : Getting user with ID 1.
	com.example.UserController               : Getting user with ID 2.

  It means for user id 2 which has not less than 12000 followers put in cache.
  
4. cli example -

127.0.0.1:6379> type users::2
string
127.0.0.1:6379> get users::2
"\xac\xed\x00\x05sr\x00\x10com.example.UsercQ\x16\x8d\n\rp\xd7\x02\x00\x03J\x00\tfollowersL\x00\x02idt\x00\x10Ljava/lang/Long;L\x00\x04namet\x00\x12Ljava/lang/String;xp\x00\x00\x00\x00\x00\x00qHsr\x00\x0ejava.lang.Long;\x8b\xe4\x90\xcc\x8f#\xdf\x02\x00\x01J\x00\x05valuexr\x00\x10java.lang.Number\x86\xac\x95\x1d\x0b\x94\xe0\x8b\x02\x00\x00xp\x00\x00\x00\x00\x00\x00\x00\x02t\x00\x05Leena"
127.0.0.1:6379>