---
layout: page
title: Webservice API
permalink: /webapi/
---
### API Token
De licentiesleutel van de applicatie is voorzien van een Web API token. Deze token is te vinden onder `beheer` > `instellingen` > `license info` > `Web API Token`.

Als hier geen token staat en/of `Web API Enabled?` als `false` staat aangegeven kun je het beste contact met [ons](/about) opnemen zodat we de licentiesleutel voor je kunnen uitbreiden.

### URL
De basis van deze url is te vinden onder `beheer` > `instellingen` > `Base URL`

De URL voor de webservice is opgebouwd volgens de volgende structuur:
* `{baseurl}/api/{entity}/{functie}.action?param1=value1&param2=value2`
* entity is de alias van de gewenste entiteit
* function is de actie die je wil uitvoeren
  * read
  * insert
  * update
  * delete
  * finish (beschikbaar als de entiteit workflowable is)
  * reopen (beschikbaar als de entiteit workflowable is)
  * login (alleen beschikbaar voor `employee`)

Concrete voorbeelden zijn:
* `http://test.smile.nl:10014/omgeving2/api/employee/insert.action?employee_username=test`
* `https://acceptatie.smile.nl/smilecomtraining1/api/call/1/update.action?call_type=15`
* `http://smile-tst.test.nl/api/department/15/delete.action`

### Authenticatie
We adviseren een dedicated user (en usergroup) aan te maken voor het gebruik van de API zodat in te regelen is wat deze gebruiker wel en niet kan.
* https://test.smile.nl/api/employee/login.action?username=test-api&password=secret&apitoken=63d169c0-1a81-11e5-b939-0800200c9a66
* Response bevat een Session token

### Authorisatie
De rechten van de gebruikte user zijn van toepassing op de API, als de gebruikte user bijvoorbeeld geen rechten heeft om meldingen te lezen is dat ook niet toegestaan via de API.
