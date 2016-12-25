# ChatScript
Natural Language tool/dialog manager

ChatScript is the next generation chatbot engine that has won the Loebner's 4 times and is the basis for natural language company for a variety of tech startups.

ChatScript is a rule-based engine, where rules are created by humans writers in program scripts through a process called dialog flow scripting. These use a scripting metalanguage (simply called a "script") as their source code. 
Here what a ChatScript script file looks like:
```
#
# file: food.top
#
topic: ~food []

#! I like spinachs
s: ( I like spinach ) 
   Are you a fan of the Popeye cartoons?

a: ( yes ) 
       I used to watch him as a child. Did you lust after Olive Oyl?
     b: ( no ) Me neither. She was too skinny.
     b: ( yes ) You probably like skinny models.

a: ( no ) What cartoons do you watch?
     b: ( none ) You lead a deprived life.
     b: ( Mickey Mouse ) The Disney icon.

#! I often eat chicken
u: ( ![ not never rarely ] I * ~ingest * ~meat ) 
   You eat meat.

u: ( !~negativeWords I * ~like * ~meat ) You like meat.

?: (do you eat _ [ ham eggs bacon]) 
   I eat '_0

?: (do you like _* or _*) 
   I don't like '_0 so I guess that means I prefer '_1.

s: ( ~like ~fruit ![~animal _bear] ) 
   Vegan, you too...

?: (do you eat _~meat) 
   No, I hate _0.

s: ( I eat _*1 >) 
  $food = '_0 
  I eat oysters.
```
Above example mentioned in article [How to build your first chatbot using ChatScript](https://medium.freecodecamp.com/chatscript-for-beginners-chatbots-developers-c58bb591da8#.2qdxjuyvs).


## Basic Features

* Powerful pattern matching aimed at detecting meaning.
* Simple rule layout combined with C-style general scripting.
* Built-in WordNet dictionary for ontology and spell-checking.
* Extensive extensible ontology of nouns, verbs, adjectives, adverbs.
* Data as fact triples enables inferencing.
* Rules can examine and alter engine and script behavior.
* Planner capabilities allow a bot to act in real/virtual worlds.
* Remembers user interactions across conversations.
* Document mode allows you to scan documents for content.
* Ability to control local machines via popen.
* Ability to read structured JSON data from websites.
* Postgres and Mongo support for big data or large-user-volume chatbots.

## OS Features

* Runs on Windows or Linux or Mac or iOS or Android
* Fast server performance supports a thousand simultaneous users.
* Multiple bots can cohabit on the same server.

## Support Features

* Mature technology in use by various parties around the world.
* Integrated tools to support maintaining and testing large systems.
* UTF8 support allows scripts written in any language
* User support forum on [Chatbots.org](https://www.chatbots.org/ai_zone/viewforum/44/) and [here](https://github.com/bwilcox-1234/ChatScript/issues)


# Getting started
## Installation

Take this project and put it into some directory on your machine (typically we call the directory ChatScript, but you can name it whatever). That takes care of installation.

```
git clone https://github.com/bwilcox-1234/ChatScript
```

## How to run locally on a console (for developement/test)
### Windows
Go to the BINARIES directory and type `ChatScript`: 
```
cd BINARIES && ChatScript
```

### Linux
```
cd BINARIES && ./LinuxChatScript64 local
```

### MacOS
```
cd BINARIES && ./MacChatScript local
```

This will cause ChatScript to load and ask you for a username. Enter whatever you want. You are then talking to the default demo bot `Harry`.

## How to run as a server (for production)
### Windows
Go to the BINARIES directory and type `ChatScript port=1024`
```
cd BINARIES && ChatScript port=1024
```
### Linux
```
cd BINARIES && ./LinuxChatScript64
```
### MacOS
```
cd BINARIES && ./MacChatScript
```

This will cause ChatScript to load as a server. 
But you also need a client (to test client-server communication). You can run a separate command window and go to the BINARIES directory and type `ChatScript client=localhost:1024` if you are on Windows, or type `./LinuxChatScript64 client=localhost:1024` if you are on Linux. This will cause ChatScript to load as a client and you can talk to the server. 

## How to build the engine.
On windows if you have Visual Studio installed, launch `VS2010/chatscript.sln` or `VS2015/chatscript.sln` and do a build. The result will go in the `BINARIES` directory.

On Linux, go stand in the SRC directory and type `make server` (assuming you have make and g++ installed). This creates BINARIES/ChatScript, which can run as a server or locally. There are other make choices for installing PostGres or Mongo.

## How to build a bot
Run ChatScript locally. From the ChatScript command prompt, type 
```
:build Harry
```

or whatever other preinstalled bot exists. If you have revised basic data, you can first do `:build 0` .

# Full Documentation
[ChatScript Wiki (user guides, tutorials, papers)](/WIKI/README.md)

# Contributing
1. Fork it
2. Create your feature branch (git checkout -b my-new-feature)
3. Commit your changes (git commit -am 'Add some feature')
4. Push to the branch (git push origin my-new-feature)
5. Create new Pull Request

# Last releases
[changes.md](/changes.md)

# Author 
* Bruce Wilcox
  * home website: [BrilligUnderstanding.com](http://www.brilligunderstanding.com)
  * mail:  [gowilcox@gmail.com](mailto:gowilcox@gmail.com )  
