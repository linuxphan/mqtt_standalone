- Install Redis, Node Redis client
sudo apt-get install redis-server redis-tools node-redis 

- Start Redis (DB) server
sudo service redis-server start

- Node install globally the mosca, bunyan, and mqtt client packages
sudo npm install mosca bunyan mqtt -g

- Change permissions of global node packages from root to your user
sudo chown -R travis:travis /usr/local/lib/node_modules

- Start Mosca standalone server with config file and bunyan standalone service
mosca -v -c server_with_redis.cfg | bunyan &

In 2 separate terminals once mosca is running - test pub/sub
- start subscribing
node sub_helloworld.js

- start publishing
node pub_helloworld.js

