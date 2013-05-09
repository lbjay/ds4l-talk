ds4l-talk
=========

Setup/Requirements
------------------
1. git clone this repo to your local environment
   * `git clone https://github.com/lbjay/ds4l-talk`
   * `cd ds4l-talk`
2. run `pip install -r requirements.txt`
   * you may need to use `sudo` for this command to work, e.g. `sudo pip install -r requirements.txt`
   * if `pymongo` fails because of missing compiler try `pip install --install-option='--no_ext' pymongo`
3. create a free MongoDB instance at https://bridge.mongohq.com/signup
   1. create account by filling out the initial signup form
   2. on the next form look for the tiny link that says "skip this step and use a free database".
   2. create a new "Sandbox" database
      * name it whatever, "ds4l", "DS4L", etc.
      * go ahead and add a user/password combo (use whatever, "foo/bar" is fine)


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
   * reading events from apache log
   * creating custom events
   * generating simple metrics
