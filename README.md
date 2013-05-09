ds4l-talk
=========

Setup/Requirements
------------------
1. clone this repo to your local environment
2. run `pip install -r requirements.txt`
   * if `pymongo` fails because of missing compiler try `pip install --install-option='--no_ext' pymongo`
3. create a free MongoDB instance at https://bridge.mongohq.com/signup
   1. create account
   2. create a new "Sandbox" database, name it "ds4l"
   3. go to Admin -> Users and add user/password combo (use whatever, "foo/bar" is fine)


Class outline
-------------
1. MongoDB
   * basic operations and commands
   * bibliographic data in MongoDB
   * aggregation and simple mapreduce example
2. Logstash
   * basic input/output
   * pubsub w/ redis
   * output to MongoDB
3. Usage data collection & analysis
   * 
