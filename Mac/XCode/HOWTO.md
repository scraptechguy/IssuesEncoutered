# Welcome to XCode HOWTO! 

Before anything else (no matter how upset with an issue you are), please go over <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/README.md" target="_blank">README.md</a> of this repo. Thanks! 

### Table of contents 

+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Mac/XCode/HOWTO.md#running-code-on-a-physical-device">Running code on a physical device</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Mac/XCode/HOWTO.md#using-apple-sf-symbols-in-swift">Using Apple SF Symbols in Swift<>

## Running code on a physical device

Yes, it has to be an iPhone... 

+ Download Apple Developer app to your device (not sure if this is a requirement, still pretty good tho)

+ Enroll in <a href="https://developer.apple.com/programs/" target="_blank">Apple Developer program</a>

+ In your XCode project, select a Developer Team (this was the most tricky part when I was setting all this up, so there's some more detail...)

In your XCode project, double click its name in the left top corner

<img width="140" alt="image" src="https://user-images.githubusercontent.com/75474651/140650917-ba2997f5-6692-426b-9954-35063d4477a5.png">

A menu will show up, in targets, select the one with the name of your project with following (iOS) 
  
<img width="163" alt="image" src="https://user-images.githubusercontent.com/75474651/140650955-4b34795e-b8be-4b21-ba00-3e8e5cf8758f.png">

There go to Signing & Capabilities and select whatever team you want. By default, personal team with your name is created
  
<img width="473" alt="image" src="https://user-images.githubusercontent.com/75474651/140650984-dfc1f3cf-90bd-41a1-aff8-4727899de316.png">

And that's it! Easy, right? Well I've been figuring that out for a week... 
  
+ Connect your iPhone to your mac with a cable 

+ In iPhone Settings, search for Developer menu. There authorise your mac 

+ In XCode Simulators pane, your iPhone name should appear. Select it and click the run button 

## Using Apple SF Symbols in Swift 

You are free to use any symbol in your app as long as you're publishing it directly to app store. Symbols may NOT be used anywhere else. You may use images with those symbols in your app campaign

+ Go to <a href="https://developer.apple.com/sf-symbols/" target="_blank">Apple Developer site</a> and download SF Symbols 3

+ Open the app and double click any symbol

+ Click on Copy Name

+ In Swift, access the symbol by...

<img width="335" alt="image" src="https://user-images.githubusercontent.com/75474651/140283299-92ff0ab5-6ba5-4db0-9b87-e3a540fd38e5.png">

You can further modify it using methods (as you would modify an image)

## Running C++ using XCode 

+ Download XCode from official <a href="" target="_blank">Apple developer site</a> or from the App Store

+ Open XCode and Create a new XCode project 

<img width="487" alt="image" src="https://user-images.githubusercontent.com/75474651/140281010-ce9ec4be-5efe-481c-abcc-88061bfe0ec4.png">

+ As a template choose Command Line Tool in macOS pane 

<img width="712" alt="image" src="https://user-images.githubusercontent.com/75474651/140281377-b9abe8ac-2a0b-4465-81a1-402423b0162b.png">

+ In options for your new project, fill in the blanks and as a language, choose C++ (all these settings can be changed later)

<img width="712" alt="image" src="https://user-images.githubusercontent.com/75474651/140281524-6a14ae1d-a21b-46f5-b925-cd5eeadc5109.png">

This will create main.cpp. We're done!

## info.plist is not there 

In XCode 13 and later, info.plist appears to be missing. Well it is, but it isn't really. TThey hid it in your project's settings! To find it... 

+ Select name of your project in top left corner

<img width="271" alt="image" src="https://user-images.githubusercontent.com/75474651/140822516-b0d3919a-53a3-4c14-94c9-406f9405e30e.png">

+ In targets, select name of your project + (iOS)

<img width="152" alt="image" src="https://user-images.githubusercontent.com/75474651/140822605-49b89d43-6c8e-4942-aa94-88fccb917a59.png">

+ Go to Info in the menu on top 

<img width="645" alt="image" src="https://user-images.githubusercontent.com/75474651/140822701-ec1064ef-1f6d-41d2-b18f-08301da11c08.png">

And you're there!

## Connecting to an existing remote in XCode

+ Create a new GitHub repo and copy the link on the top of the page 

<img width="1201" alt="image" src="https://user-images.githubusercontent.com/75474651/141649877-b0514853-a070-4ae6-a952-1fe1266f495e.png">

+ In XCode on the left pane menu, click on the weird square (second from left), and go to Repositories 

<img width="268" alt="image" src="https://user-images.githubusercontent.com/75474651/141649927-7c02def0-2296-4e18-b29c-4ec971cbc68b.png">

+ There double click Remotes (the last one) and select Add Existing Remote...

<img width="338" alt="image" src="https://user-images.githubusercontent.com/75474651/141649966-57ff40bf-00e4-4ebd-bc56-df9e007520e5.png">

+ A popup will show up, keep the name and paste your link from earlier to Location

<img width="469" alt="image" src="https://user-images.githubusercontent.com/75474651/141650019-4359e5f0-923a-4e7f-8365-198df293c20d.png">

+ Then click add and under Source Control on top push on GitHub, we're done! 

<img width="581" alt="image" src="https://user-images.githubusercontent.com/75474651/141650065-2f74b5c5-fd9a-4b10-ac05-13fd5f7b7d3c.png">

(don't include tags)

### XCode GitHub contributions won't show in your repo 

+ In XCode pull your GitHub repo first 

+ Then push changes 
