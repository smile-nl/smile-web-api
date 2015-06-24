---
layout: page
title: Webservice API
permalink: /webapi/
---
### API Token
De licentiesleutel van de applicatie is voorzien van een Web API token. Deze token is te vinden onder `beheer` > `instellingen` > `license info` > `Web API Token`.

Als hier geen token staat en/of `Web API Enabled?` als `false` staat aangegeven kun je het beste contact met [ons](/about) opnemen zodat we de licentiesleutel voor je kunnen uitbreiden.

### URL
De SmileCom webservice wordt aangeroepen met een HTTP request met post of get parameters, het resultaat wordt gepresenteerd in json formaat. De basis van deze url is te herleiden van de url van de applicatie.

Als je ingelogd bent in de SmileCom applicatie staat er bovenin de adres balk een url die lijken op éém van de volgende url's:
* `http://test.smile.nl:10014/omgeving2/Main.action?prv=1&fnc=100&form=807`
* `https://acceptatie.smile.nl/smilecomtraining1/Main.action?fnc=401&prv=2`
* `http://smile-tst.test.nl/Main.action?fnc=405&prv=8`

Het deel vanaf het begin tot en met de laatste `/` is de basis url. De URL voor de webservice is opgebouwd volgens de volgende structuur:

* `{basisurl}/api/{entity}/{functie}.action?param1=value1&param2=value2`
* entity is de alias van de gewenste entiteit
* function is de actie die je wil uitvoeren
  * read
  * insert
  * update
  * delete
  * finish
  * reopen  

Op basis van de bovenstaande voorbeeld url's zijn dit mogelijke url's
* `http://test.smile.nl:10014/omgeving2/api/employee/insert.action?employee_username=test`
* `https://acceptatie.smile.nl/smilecomtraining1/api/call/1/update.action?call_type=15`
* `http://smile-tst.test.nl/api/department/15/delete.action`
