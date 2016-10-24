Electrode OTA Server Manager Plugin
===
The electrode-ota-server-manager  is a UI plugin for the server giving clients a ui for managing there applications. The UI is based on [electrode-ota-ui](../../../electrode-ota-ui)

## Installation

```sh
$ npm install --save electrode-ota-server-manager

```

## Usage
To use the server manager you need to set a few things up.
First in your development.json or production.json
```js
{

  "plugins": {
    "inert": {
      "enable": true
    },
    "electrode-ota-server-dao-cassandra": {
      //see electrode-ota-server for config
    },
    "electrode-ota-server-auth": {
      //see electrode-ota-server for config
    },
    //adds management to the login option
    "electrode-ota-server-routes-auth": {
      "options": {
        "providers": [
          {
            "name": "github",
            "auth": "github-oauth",
            "label": "GitHub",
            "icon": {
              "src": "https://assets-cdn.github.com/images/modules/logos_page/GitHub-Mark.png",
              "height": 50,
              "width": 50
            }
          },
          {
            "name": "manager/login",
            "auth": "github-oauth",
            "label": "Management",
            "redirectTo": "/manager",
            "canRegister":false,
            "icon": {
              "src":"/manager/assets/electrode-logo.png",
              "height": 50,
              "width": 50
            }
          }
        ]
      }
    },
    //initialize electrode-ota-server-manager
    "electrode-ota-server-manager": {

    }
  }
}


```
## Then start the server
```sh
 $ npm start
``

## License

Apache-2.0 © [WalmartLabs](https://github.com/electrode-io/electrode-ota-server-manager)

