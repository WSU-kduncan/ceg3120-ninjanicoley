Setup
To get the API, first we must start a new application on the Discord Developer Portal. 
A Discord account is required. 
The application area allows you to interact with Discord's APIs.
So we create the application, name it, and then create it. 
We then create the bot and add the bot to the application. 
Then add the bot to guild/server by going to the OAuth2 page which hit Discords OAuth2 API and authprizes the API to access your applications credentials.
We have to grant our application's bot user access to Discord APIs using the application's OAuth2 credentials so we select SCOPES and Admin permissions. 
We then will copy the URL generated  and select our guild, and then authorize it!
Take the token thats created near the bot and insert it into the .env file you created in the DISCORD_TOKEN section. 
In order to run the code, some packages that need to be installed include dotenv with pip using "pip3 install -U python-dotenv"
and "pip3 install -U discord.py"

Usage
-with your changes to the code in place, describe
-what commands you can type in your Discord server
-what response this will provide (from your bot)

Research
A possible way to not have to manually run the bot each time is to have it run 24/7. To do this, you would need to go with a third-party Virtual Private Server (VPS). Since it is virtual, it can run 24/7. 
A good source on how to do this in under 1 hour is: 
https://www.writebots.com/discord-bot-hosting/