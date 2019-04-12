# MuleSoft Coin Collector Game using ObjectStore & Flow Designer

This game is to showcase how to use MuleSoft's ObjectStore Connector in Flow Designer.  I developed the game using the Phaser open source HTML5 game engine.  MuleSoft is an integration platform that allows you to connect SaaS & enterprise applications in the cloud or on-premise. In this code example, MuleSoft's AnyPoint Platform is powering the backend of the game.  Every time you collect a coin, a *POST* request is made to the AnyPoint platform which decodes the JSON from a string, then grabs the current value from the ObjectStore (also known as a KV store), and then interates by 1 to the current value in the ObjectStore, and stores the new value to the ObjectStore.  All clients that have the application open will be able to see the database value in the top right of the screen change in real-time.

Download and clone my repo to try it yourself :)

## Installation

To run on your local machine, make sure to use [NodeJS](https://nodejs.org/en/) and then install [Express](https://expressjs.com/) to get around a CORS error which occurs when you try to host this application on localhost.  When running locally, run the mulegame.js file which will render the html file on your local express server. 

Run the following command to launch the express server:
```
node mulegame.js
```

```javascript
var express = require('express');
var app = express();

app.use(express.static('./'));

app.get('/', function(req, res) {
    res.render('index.html');
});

app.listen(8882, '127.0.0.1')

```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)