# App-Config-Loader
Takes db config from either the command line or .env file and returns app configuration for the periodic app.
* Command Line
```
$ node index.js -e development --db_config.settings.name=Test App --db_config.configuration.type=db --db_config.configuration.db=lowkie --db_config.configuration.options.dbpath=content/config/settings/config_db.json
```
* .env file
  * create a env file in the app_root with DB_CONFIG set to configurations in JSON format
```
Example .env

DB_CONFIG={
 "settings": {
    "name": "Test App Config"
  }, 
  "db_config":{
    "type": "db", 
    "db":"lowkie", 
    "options":{
      "db_path": "content/config/settings/config_db.json"
    }
  }
}

```
* Default
``` javascript 
{
  configuration: {
    'type': 'db',
    'db': 'mongoose',
    'options': {
      'url': 'mongodb://localhost:27017/config_db',
      'connection_options': {},
     },
   },
  settings: {
    name: 'Sample App',
  },
}
 ```
