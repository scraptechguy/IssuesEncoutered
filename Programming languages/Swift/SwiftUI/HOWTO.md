# Welcome to SwiftUI HOWTO! 

Before anything else (no matter how upset with an issue you are), please go over <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/README.md" target="_blank">README.md</a> of this repo. Thanks! 

### Table of contents

+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#maximum-number-of-views-exceeded">Maximum number of views exceeded</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#scrollbar-in-scrollview-is-annoying">ScrollBar in ScrollView is annoying</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#align-text-to-block">Align text to block</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#adding-and-removing-views-with-animation">Adding and removing views with animation</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#vertical-swipable-views">Vertical swipable views</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#simultaneous-button-gestures">Simultaneous button gestures</a>

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

<a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#welcome-to-swiftui-howto">Table of contents</a>

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
