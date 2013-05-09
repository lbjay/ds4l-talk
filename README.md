ds4l-talk
=========

Setup/Requirements
------------------
1. git clone this repo to your local environment
   * `git clone https://github.com/lbjay/ds4l-talk`
   * `cd ds4l-talk`
2. run `pip install -r requirements.txt`
   * you may need to use `sudo` for this command to work, e.g. `sudo pip install -r requirements.txt`
   * if `pymongo` fails because of missing compiler try `pip install --install-option="--no_ext" pymongo`
3. create a free MongoDB instance at https://bridge.mongohq.com/signup
   1. create account by filling out the initial signup form
   2. on the next form look for the tiny link that says "skip this step and use a free database".
   2. create a new "Sandbox" database
      * name it whatever, "ds4l", "DS4L", etc.
      * go ahead and add a user/password combo (use whatever, "foo/bar" is fine)


Class outline
-------------
1. MongoDB
   1. basic operations and commands
      1. connect via MongoClient
         * `from pymongo import MongoClient`
         * `mongo = MongoClient('mongodb://<user>:<password>@dharma.mongohq.com:10045/ds4l')
      1. examine the db and collection commands
         * `db = mongo.ds4l`
         * `coll = db.foo`
      1. inserts, queries, cursors, updates
         * `coll.insert({'a': 1, 'b': 2, 'c': 3})`, ...
         * `coll.find_one({'b': 2})`, ...
         * `c = coll.find({})`, ...
         * `coll.update({'a': 1}, {'$set': {'c': 4}})`, ...
         * `coll.insert({'a': 1, 'd': {'foo': 'bar', 'baz': [1,2,3]}})`, ...
   1. bibliographic data in MongoDB
      1. import fdocs.json
         * `mongoimport -h dharma.mongohq.com:10045 --db ds4l --collection=fdocs -u<user> -p<pass> < fdocs.json`
      1. example queries
         * `fdocs.find({'refereed': True}).count()`
         * `fdocs.find({'references': '2003ApJ...584L..13F'}).count()`
         * `fdocs.find({'references': { '$all': ['2003ApJ...584L..13F','2003ApJ...589L..41S']}}).count()`
         * `fdocs.find({'citation_count': {'$gt': 10}}).count()`
         * `fdocs.find({'$where': 'this.references.length > 30'}).count()`
   1. aggregation and simple mapreduce example
1. Logstash
   1. basic input/output
      
   1. pubsub w/ redis
   1. output to MongoDB
1. Usage data collection & analysis
   * reading events from apache log
   * creating custom events
   * generating simple metrics
