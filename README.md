# App-Config-Loader [![Build Status](https://travis-ci.com/digifi-io/app-config-loader.svg?token=1owHdFhQpzdjTsye6Ykz&branch=master)](https://travis-ci.com/digifi-io/app-config-loader) [![Coverage Status](https://coveralls.io/repos/github/digifi-io/app-config-loader/badge.svg?branch=master&t=5DBAAg)](https://coveralls.io/github/digifi-io/app-config-loader?branch=master)
Takes db config from either the command line or .env file and returns app configuration for the periodic app.


## Getting Started

To begin using the app-config-loader, install the module by running the following command:

```
$ npm install @digifi/app-config-loader --save
```

## Usage

After installing the app-config-loader, require the module at the top of files where you would like to use it.

```
const app_config_loader = require('@digifi/app-config-loader');
```
### Command Line
#### Example Config
```
$ node index.js -e development --db_config.settings.name=Test App --db_config.configuration.type=db --db_config.configuration.db=lowkie --db_config.configuration.options.dbpath=content/config/settings/config_db.json
```
### .env file
Create a env file in the app_root with DB_CONFIG set to configurations in JSON format
#### Example Config
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

### Default Config
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
