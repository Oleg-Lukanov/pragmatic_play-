# pragmatic_play-

The “build.js” file describes many actions and combinations the game can produce [screenshot](http://sc.com.ly/show/b7cb67de-be2f-4526-87ff-896fc7c0c742). I described a few of them using the Postman API. A "gameService" request can have different "actions" in the request body:
"doInit"
"doSpin"
"doCollect"

-  First I intercept the "mgckey" token in the “openGame.do” redirect request,
- After to start the game we send the request "doInit"
- Then we simulate the rotation of the drum by sending the request "doSpin"
- In case of a win (tw > 0), we send a request to update the balance "doCollect" and then again "spin the drum" "doSpin"

Postman Collection (https://www.getpostman.com/collections/c2f9dd39a4347d7dc242)
Checklist (https://docs.google.com/spreadsheets/d/1KRZN9jVFEtDLodIqr7IVn9_EdpGdZC6qAzkL1oM56r8/edit?usp=sharing)

There are also errors in the response body:
"undefined (action invalid)"
"unlogged"
"Internal server error. The game will be restarted. SystemError"

There are two folders in the Postman collection, I described each request separately and how they work together. I used pre-requests, tests, requests in tests, and environment variables

“openGame.do” - sends a request to get a token "mgckey" and redirects to the DOM html5Game.do
“gameService” - the main game control request

“html5Game.do” - loads the DOM
“stats.do” - send environment to server
“collect” - Google counter looks like
“reloadBalance.do” - periodically checks the balance
“saveSettings.do” - sends settings to the server

The rest of the requests are probably secondary to the logic of the game
