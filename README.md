# QlikBotNode ![Qlik Sense Bot](/screenshots/general/QS_Hub_thumb.png?raw=true "Qlik Sense Bot")
- QlikBotNode is a server build in nodejs, expressjs and MySql that connects to chat and media platforms like Telegram, Skype, MS Teams, Cortana, Slack, Google Assistant and Amazon Alexa. 
- It connects to MySql and stores the users for a mass messaging at any time
- Commands, are case sensitive

# Getting started

### Prerequisites 

Before continuing, make sure that you have these tools installed:

- Node.js >= 7.0
- MySql >=14
- Git bash if on Windows
- Certificates for running https. If your environment is dev, then you can export from Qlik Sense Enterprise for "localhost" in a "Platform Independent PEM-format". Save them under app/server/certs/localhost/
![Exporting Certificates with Sense](/screenshots/general/export-certificates.png?raw=true "Exporting Certificates with Sense")
- QVFs needed:
	- Helpdesk: This comes with every Qlik Sense Desktop installation. You will find it under C:\Users\{username}\Documents\Qlik\Sense\Apps\Helpdesk Management.qvf
	- Salesforce: https://github.com/yianni-ververis/Salesforce/tree/master/Files
	- Cio Dashboard: https://github.com/yianni-ververis/CIO/tree/master/Files
- Once uploaded to the Qlik Sense Enterprise, get the app ids from the QMC and with the your host DNS put them in the app/server/config.js

And know of at least some of these web technologies:

- JavaScript
- Promises
- Websockets

### Usage

- To start, install all of necessary packages
```javascript
npm install
```

- Install all the required Environmental variables for each of the chat platforms.
	- For Windows, go to "Control Panel" -> "System" -> "Advanced System Settings" -> "Environment Variables"
	- For Linux, from your directory (~), type "nano .bash_profile" or "vim .bash_profile" and enter the variables there like 
		- "export TELEGRAM_BOT_TOKEN=######"

- For Database storage and mass Instant Messaging, create a database and run the files/sensebot.sql

- Then, 
	- for local testing, type gulp or,
	- for production, run the server with [forever.js](https://github.com/foreverjs/forever) by typing 
	```javascript
	forever start foreverConfig.json
	```
	- Make sure you have the right certificates under app/server/certs/


This will start your server at https://localhost:3000

### Features

- Build with Operating System agnostic, nodejs. It can be installed and run in Windows IIS and desktop, Linux and mac
- Scalable. Sense-bot has its own models and routes. You can add as many as you want in your api server
- Professional logging solution that records every step into the log and saves the file based on the date. This gives you more flexibility over debugging.
- Latest Open Source [Enigma.js](https://github.com/qlik-oss/enigma.js) wrapper for the Qlik Sense Engine API
- Robust MySql for user storing and mass IM sending.

### Messaging Platforms
---
- **[Telegram](docs/Telegram.md)**
- **MS Skype**
- **MS Teams**
- **MS Cortana**
- **Slack**
- **Google Assistant**
- **Amazon's Alexa**
---

### Files
- [List of all files](docs/files.md)

### Version Log
- [Log](docs/log.md)

### Contributing

- Make sure you have completed all of the steps in [Open Source at Qlik](https://github.com/qlik-bots/open-source) or [Open Source at Qlik](https://github.com/qlik-oss/open-source)
- Make sure that your working branch is ```v1``` and not ```master``` 
- Run ```gulp lint``` and make sure the code is without errors and warnings before committing
- All variables are camelCase but the database fields are with underscore like `user_id`
- All routes are lower case but models are Capitalized
- No spaces. Set your files to use `Tab Size:4`
- Do not declare variables that are not used
- Do not forget console.log() or any other debugging commands in your code
- When creating new Modules, add jsDoc syntax for `@module {name}`, `@author {your_email@domain.com}` and `@description {your_short_description}`. Then run gulp jsdoc to generate the new files in the docs/files.md
- Once committed, do a pull-request for reviewing and merging.

### Copyright
Copyright 2017 QlikTech International AB

Licensed under the Apache License, Version 2.0 (the "License");you may not use this file except in compliance with the License.You may obtain a copy of the License at    

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, softwaredistributed under the License is distributed on an "AS IS" BASIS,WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.See the License for the specific language governing permissions andlimitations under the License.

