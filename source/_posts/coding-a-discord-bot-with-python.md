---
title: Coding a Discord Bot With Python!
subtitle: A simple walkthrough of using discord.py on replit
toc_nav_num: true
date: 04-21-2020 12:00:00
catalog: true
header-img: ""
top: 1
tags:
- discord.py
- discord
- python
- coding
- hehe
- AwesomeAg
- replit
- uptime robot
---
So... you've probably heard of discord, a chat and stream app for gamers. Over time it has evolved but it is still there for one main thing: chatting. Nowdays, you can create bots for discord that act as users and put some fun into discord with games, moderation, and trolling. Bots can be coded in many different languages, and it's pretty common to make one in discord.js or discord.py. 
![A bot](https://media.discordapp.net/attachments/702244544321945671/702244622377943080/unknown.png)
To start, you need to open repl.it and start a new python code. Write
```python
import discord
```
on the first line
but before that, go to the packages section and search discord to install it. 
To host the bot, create a new file and name it keep_alive.py. Now type the following into the file
```python
from flask import Flask
from threading import Thread
app = Flask('')
@app.route('/')
def main():
    return "Bot is online"
def run():
    app.run(host="0.0.0.0", port=8080)
def keep_alive():
    server = Thread(target=run)
    server.start()
```
now go back to main.py. 
Before you start coding, you need to create the actual discord bot. you can do this by going [here](https://discordapp.com/developers/applications)
and then press the button that says new application in the top right:
![New app button](https://media.discordapp.net/attachments/702244544321945671/702259415155474552/unknown.png)
Name it whatever you want, but when you're done, go to the section that says bot
![bot button](https://media.discordapp.net/attachments/702244544321945671/702259890529239150/unknown.png)
and click it.
You should see a screen like this ![screen with bot](https://media.discordapp.net/attachments/702244544321945671/702260048029679656/unknown.png?width=1913&height=685)
Now to bring it to life, press add bot and then press "yes do it". You can name it and edit the profile picture, but the big part is copying the token ![copy token](https://media.discordapp.net/attachments/702244544321945671/702260590516633701/unknown.png)
now head back to the main.py file and at the end of it, write the following:
```python
import keep_alive #this should be the name of the file that you created earlier
keep_alive.keep_alive()
await bot.run("TOKEN") #replace token with your token. 
```
now head back to the beginning of the file, where you imported discord. There, type
```python
client = discord.Client()
bot = commands.Bot(command_prefix="!", description='My new bot!') #You can change the prefix if you wanr
```
Congrats! You have officially made your discord bot! It doesn't do anything yet, but one last step before we finish is inviting it to a server.
If you scroll to the bottom of the OATH2 page (the sidebar next to bot), you will see this: ![panel](https://media.discordapp.net/attachments/702244544321945671/702262422823632896/unknown.png?width=1913&height=683)
click on "bot" and another panel will appear. On this new panel, click "Administrator" and copy the generated link at the bottom.
![panel2](https://media.discordapp.net/attachments/702244544321945671/702262834385387571/unknown.png?width=1649&height=917)
![link](https://media.discordapp.net/attachments/702244544321945671/702262965235220600/unknown.png?width=1913&height=85)
go to the link you copied and invite it to a server. I would recommend making a testing server for this. 
PERFECT! Your bot is up on a server, but it doesn't do anything yet 😞. Well, stay tuned for part 2 on how to make commands, send embeds, and more! [Go ahead and check the code here](https://repl.it/@AgastyaSandhuja/discord-bot-how-to-1)
[discord.py documentation (the docs)](https://discordpy.readthedocs.io/)