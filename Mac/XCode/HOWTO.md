## Running code on a physical device

Yes, it has to be an iPhone... 

+ Download Apple Developer app to your device (not sure if this is a requirement, still pretty good tho)

+ Enroll in <a href="https://developer.apple.com/programs/" target="_blank">Apple Developer program</a>

+ In your XCode project, select a Developer Team (this was the most tricky part when I was setting all this up, so there's some more detail...)

In your XCode project, double click its name in the left top corner

<img width="140" alt="image" src="https://user-images.githubusercontent.com/75474651/140650917-ba2997f5-6692-426b-9954-35063d4477a5.png">

A menu will show up, in targets, select <name of your project> (iOS)
  
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

