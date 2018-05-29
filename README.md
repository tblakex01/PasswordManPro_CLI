# Password Manager PRO - Commandline interface

[![Build Status](https://travis-ci.org/rmetcalf9/PasswordManPro_CLI.svg?branch=master)](https://travis-ci.org/rmetcalf9/PasswordManPro_CLI)
[![PyPI version](https://badge.fury.io/py/passwordmanpro_cli.svg)](https://badge.fury.io/py/passwordmanpro_cli)

Python based command line interface for [Password Manager Pro](https://www.manageengine.com/products/passwordmanagerpro/help/restapi.html). This provides a command line interface which uses the REST API to provide a command line to:

 - Read individual passwords
 - Create temporary files with a set of passwords


# Setup

Python and pip must be installed on the machine you wish to use.

 1. Create a API user in [Password Manager Pro](https://www.manageengine.com/products/passwordmanagerpro/help/restapi.html)
 2. Set the PASSMANCLI_AUTHTOKEN enviroment variable based on the user (Alternativly set PASSMANCLI_AUTHTOKENFILE if you wish to load the key from a file)
 3. Set the PASSMANCLI_URL enviroment variable based on your install of password manager pro
 4. Install utility (pip3 install PasswordManPro_CLI
 
# Usage

## Access single password

```
passwordmanpro_cli get **RESOURSE_NAME** **PASSWORD_NAME**
```

## Generate password file

```
passwordmanpro_cli javaprops **FILTER** > somefile.properties
```

## Directly access the API

The previous functions were created for convience because the API uses resourse ID and password ID rather than the names. To provide further flexibility the rawget command is provided which allows users to call apis. (The auth token is added invisibly based on enviroment paramaters)

```
passwordmanpro_cli rawget **URL**
```

Exmaple:
```
passwordmanpro_cli rawget /restapi/json/v1/resources
```



