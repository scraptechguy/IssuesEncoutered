# Welcome to SwiftUI HOWTO! 

Before anything else (no matter how upset with an issue you are), please go over <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/README.md" target="_blank">README.md</a> of this repo. Thanks! 

## Maximum number of views exeeded 

+ In SwiftUI, maximum number of views (elements) in a container is 10. One element could be Spacer() or a button. To resolve this, group views together:

```swift
Group {
    <code>
}
```
