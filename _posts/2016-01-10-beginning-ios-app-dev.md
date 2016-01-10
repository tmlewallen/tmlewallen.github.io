---
layout: post
title: iOS Development as a Newbie
meta: Trial and Error
tags: [dev, ios]
post-id: f 
---

After taking two online courses regarding iOS development, I've finally started venturing out on my own. My goal is to create a sort-of like a text based adventure, except with audio dialogue instead of text and user interactions are simply swipes and taps. 

![Moving around locations one, two, and three](/assets/Movement.png)_Moving between locations one, two, and three_

So far so good! As of now, I have an app that builds the world map from a JSON config file and navigates from location to location via swipes. Additionally, each location is associated with an audio file that plays when you visit the location.

![Config File](/assets/TestConfig.png)_Demo JSON Config File_

I'm pretty pleased with how far I've gotten, but I faced a lot of challenges getting it all working. Thankfully, Swift has some build in functionality for JSON parsing. But what continues to be one of the main hurdles is just working in an unfamiliar environment. For example, I wanted to print out the NSDictionary that is returned from parsing my JSON file. So I think, "Well, I'll just call 'toString'". Well, of course, there is no "toString" method. But there _is_ a "description" property, which does the same thing: returns a string representation of the object... So I found what I was looking for (not before testing out an extension to print out the contents of an NSDictionary), but I would've never used the word "description" to describe what a String representation of an Object should be. But hey, all I've really ever known is Java, so what do I know?

![Guarding Optionals and Throwing Exceptions](/assets/GuardingOptionals.png)_Guarding Optionals and Throwing Exceptions_

Another thing that has been tripping me up is Exception Handling. So I'm on board with Optionals and handling them, it just feels weird to have to handle thrown Errors/Exception AND unwrapping optionals in different ways. They seem pretty similar to me. This let me to start looking at 'try-catch' blocks in Swift and to using 'guard' with my optionals. If guard fails, I throw an exception. This way, I consolidate all my errors/unwraps in to one or more catch blocks. When unwrapping lots of optionals (like when you're checking for properties in a dictionary), this 'guard-throw' pattern looks a lot cleaner than a ton of nested 'if-let' statements. 

Xcode is also acting up a bit. I've had two different instances of an error notification persisting after I've already fixed the issue. As I've now found out, building/running the app generally gets rid of these, but dang are they nearly impossible to get rid of otherwise. 

Overall, so far so good. Now I just have write and record a whole story to go with it. 