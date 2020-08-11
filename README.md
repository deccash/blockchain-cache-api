# TurtlePay™ Blockchain Cache API

#### Master Build Status
[![Build Status](https://travis-ci.org/TurtlePay/blockchain-cache-api.svg?branch=master)](https://travis-ci.org/TurtlePay/blockchain-cache-api) [![Build status](https://ci.appveyor.com/api/projects/status/github/TurtlePay/blockchain-cache-api?branch=master&svg=true)](https://ci.appveyor.com/project/brandonlehmann/blockchain-cache-api/branch/master)

## Prerequisites

* MariaDB/MySQL with InnoDB support
* [TurtlePay: Blockchain Data Collection Agent](https://github.com/TurtlePay/blockchain-data-collection-agent)
* [Node.js](https://nodejs.org/) LTS

## Foreword

We know that this documentation needs cleaned up and made easier to read. We'll compile it as part of the full documentation as the project works forward.

## Setup

1) Clone this repository to wherever you'd like the API to run:

```bash
git clone https://github.com/TurtlePay/blockchain-cache-api
```

2) Install the required Node.js modules

```bash
cd blockchain-cache-api && npm install
```

3) Use your favorite text editor to change the values as necessary in `config.json`

**Note:** Make sure you use a read-only database user for security reasons

  
```javascript
{
  "mysql": {
    "host": "localhost",
    "port": 3306,
    "username": "root",
    "password": "password",
    "database": "turtlecoin",
    "connectionLimit": 10
  },
  "bindIp": "0.0.0.0",
  "httpPort": 80,
  "corsHeader": "*"
}
```

4) Fire up the script

```bash
node index.js
```

5) Optionally, install PM2 or another process manager to keep the service running.

```bash
npm install -g pm2@latest
pm2 startup
pm2 start index.js --name blockchain-cache-api -i max
pm2 save
```

## API

See https://docs.turtlepay.io/blockapi/ for the full REST API provided by this package.

###### (c) 2018 TurtlePay™ Development Team
