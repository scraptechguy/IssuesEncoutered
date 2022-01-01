# Welcome to SwiftUI HOWTO! 

Before anything else (no matter how upset with an issue you are), please go over <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/README.md" target="_blank">README.md</a> of this repo. Thanks! 

### Table of contents

+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#maximum-number-of-views-exceeded">Maximum number of views exceeded</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#scrollbar-in-scrollview-is-annoying">ScrollBar in ScrollView is annoying</a>

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
