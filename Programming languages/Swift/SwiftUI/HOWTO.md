# Welcome to SwiftUI HOWTO! 

Before anything else (no matter how upset with an issue you are), please go over <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/README.md" target="_blank">README.md</a> of this repo. Thanks! 

### Table of contents

+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#maximum-number-of-views-exceeded">Maximum number of views exceeded</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#scrollbar-in-scrollview-is-annoying">ScrollBar in ScrollView is annoying</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#align-text-to-block">Align text to block</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#adding-and-removing-views-with-animation">Adding and removing views with animation</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#vertical-swipable-views">Vertical swipable views</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#simultaneous-button-gestures">Simultaneous button gestures</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#userdefaults">UserDefaults</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#preview-provider-bugs">Preview provider bugs</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#freezing-a-header">Freezing a header</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#execute-function-on-start-up">Execute function on start up</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#lock-app-in-portrait">Lock app in portrait</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#aminations">Animations</a>


## Maximum number of views exceeded 

+ In SwiftUI, maximum number of views (elements) in a container is 10. One element could be Spacer() or a button. To resolve this, group views together:

```swift
Group {
    <code>
}
```

## ScrollBar in ScrollView is annoying 

+ By default when ScrollView exceeds screen size, ScrollBar shows. To hide it, add this to your ScrollView

```swift
ScrollView(showsIndicators: false) {
    <code>
}
```


## Align text to block

+ This sounds and is stupid, but learned about such a thing after 2 months of using SwiftUI. To align text to block, use the following method:

```swift
Text("Hello, World!")
    .multilineTextAlignment(.center)
```


## Adding and removing views with animation

```swift
struct HomeView: View {
    @State private var showingInfo:Bool = false

    var body: some View {
        VStack {
            Button("Press to show more info") {
                withAnimation {
                    showingInfo.toggle()
                }
            }

            if showingInfo {
                Text("You suck lol.")
            }
        }
    }
}
```


## Vertical swipable views

+ In `<project name>App` file:

```swift
import SwiftUI

@main
struct <project name>App: App {
    var body: some Scene {
        WindowGroup {
            TabView {
                PurpleView()
                    .environmentObject(ContentModel())
                    
                PinkView()
                    .environmentObject(ContentModel())
            }.tabViewStyle(PageTabViewStyle())
        }
    }
}
```


## Simultaneous button gestures

+ SwiftUI allows you to add more than one button gesture. In this case it's click and hold for 0.7 seconds or longer. 

```swift
Button(action: {
            if model.isLongPressing == true {
            model.isLongPressing.toggle()
            }
                        
            else {
                model.count += 1
            }
                
            model.checkTextSize()
        },
        label: {<code>}).simultaneousGesture(LongPressGesture(minimumDuration: 0.7).onEnded { _ in
                            model.isLongPressing = true
                    
                            model.count = 0
                        })
```


## UserDefaults

+ UserDefaults are used to store data even after application is closed. Property wrappers are not allowed in top level code, otherwise it doesn't really matter where you declare UserDefaults.

```swift
class ContentModel: ObservableObject {
    @AppStorage("guideStatus") var guideShown: Bool = false
    
    func changeGuideStatus() {
        guideShown = true
    }
}
```

Usage example:

```swift
Button(action: {model.changeGuideStatus()}, label: {Text("Continue")})
```


## Preview provider bugs

### Using EnvironmentObject wrappers

+ When using EnvironmentObject wrappers make sure to add `.environmentObject(ContentModel())` to PreviewProvider struct as well. 

```swift
struct HomeView_Previews: PreviewProvider {
    static var previews: some View {
        HomeView()
            .environmentObject(ContentModel())
    }
}
```


## Freezing a header 

+ To make the header not move while scrolling, you can do the following:

```swift
        ScrollView {
            LazyVStack(alignment: .leading, pinnedViews: [.sectionHeaders]) {
                Section(header: Text("Restaurants").bold()) {
                    ForEach(model.restaurants) {business in
                        Text(business.name ?? "")

                        Divider()
                    }
                }
                
                Section(header: Text("Sights").bold()) {
                    ForEach(model.sights) {business in
                        Text(business.name ?? "")
                        
                        Divider()
                    }
                }
            }
        }
```


## Execute function on start up

+ To execute a function before a view is shown, do the following: 

```swift
    HomeView()
        .onAppear(perform: <your function>)
```


## Lock app in portrait

+ To lock your app in portrait, go to your project option (click on your project name with the blue icon next to it in Xcode)

+ Go to targets section 

![image](https://user-images.githubusercontent.com/75474651/152373486-fc79846d-b346-40c3-9eec-b395a30dc2aa.png)

+ There proceed to Build Settings and look for Info.plist Values section 

![image](https://user-images.githubusercontent.com/75474651/152373742-83c6db2b-855c-477b-a0cb-d18d25afa460.png)

+ And change Supported Interface Orientations to UIInterfaceOrientataionPortrait only


## Animations

```
https://youtu.be/52Otx3xDGUo
```


<a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#welcome-to-swiftui-howto">Table of contents</a>
