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
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#animations">Animations</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#concepts">Concepts</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#widgets">Widgets</a>


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


## Concepts

### HomeView Concept

```swift
import SwiftUI

struct HomeViewConcept: View {
    // Access data in ContentModel.swift
    
    @EnvironmentObject var model: ContentModel
    
    
    @State var offset: CGSize = .zero
    @State var showingSettings:Bool = false
    
    var body: some View {
        ZStack {
            model.bg.overlay(
                    Text("rest of the homeview")
                        .foregroundColor(model.fontClr)
                )
                .clipShape(LiquidShape(offset: offset))
                .overlay(
                    Image(systemName: "gearshape")
                        .font(.system(size: model.screenSize.width / 18))
                        .frame(width: model.screenSize.width / 8, height: model.screenSize.width / 8)
                        .contentShape(Rectangle())
                        .gesture(DragGesture().onChanged({ (value) in
                            withAnimation(.interactiveSpring(response: 0.7, dampingFraction: 0.6, blendDuration: 0.6)){
                                    offset = value.translation
                            }
                        }).onEnded({ (value) in
                            withAnimation(.spring()) {
                                if -offset.width > model.screenSize.width / 2 {
                                    offset.width = -model.screenSize.height
                                    showingSettings.toggle()
                                }
                                
                                else {
                                    offset = .zero
                                }
                            }
                        })
                        )
                        .foregroundColor(model.objectsClrDark)
                        .offset(x: model.screenSize.width / 50, y: model.screenSize.width / 3.6)
                        .opacity(offset == .zero ? 1 : 0),
                    alignment: .topTrailing
                )
                .ignoresSafeArea()
            
            if showingSettings == true {
                Text("show home")
                    .onTapGesture {
                        withAnimation(.spring()) {
                            offset = .zero
                            showingSettings.toggle()
                        }
                    }
            }
        }
    }
}

struct LiquidShape: Shape {
    
    var offset: CGSize
    
    var animatableData: CGSize.AnimatableData {
        get {return offset.animatableData}
        set {offset.animatableData = newValue}
    }
    
    func path(in rect: CGRect) -> Path {
        return Path {path in
            let width = rect.width + (-offset.width > 0 ? offset.width: 0)
            
            path.move(to: CGPoint(x: 0, y: 0))
            path.addLine(to: CGPoint(x: rect.width, y: 0))
            path.addLine(to: CGPoint(x: rect.width, y: rect.height))
            path.addLine(to: CGPoint(x: 0, y: rect.height))
            
            let from = 80 + (offset.width)
            path.move(to: CGPoint(x: rect.width, y: from > 80 ? 80: from))
            
            var to = 180 + (offset.height) + (-offset.width)
            to = to < 180 ? 180: to
            
            let mid: CGFloat = 80 + ((to - 80) / 2)
            path.addCurve(to: CGPoint(x: rect.width, y: to), control1: CGPoint(x: width - 50, y: mid), control2: CGPoint(x: width - 50, y: mid))
        }
    }
}

struct HomeViewConcept_Previews: PreviewProvider {
    static var previews: some View {
        HomeViewConcept()
    }
}
```

## Confetti

```swift
import SwiftUI

struct Home_Previews: PreviewProvider {
    static var previews: some View {
        Home()
    }
}


struct Home: View {
    // Access data in ContentModel.swift
    
    @EnvironmentObject var model: ContentModel
    
    
    @State var wish = false
    // Finish Wishes..
    @State var finshWish = false
    
    var body: some View{
        
        ZStack {
            
            VStack(spacing: 30){
                Button(action: doAnimation, label: {
                    Text("Confetti GO!")
                })
                .disabled(wish)
                
            }
            
            EmitterView()
                .scaleEffect(wish ? 1 : 0, anchor: .top)
                .opacity(wish && !finshWish ? 1 : 0)
                // Moving From Center Effect...
                .offset(y: wish ? 0 : getRect().height / 2)
                .ignoresSafeArea()
        }
    }
    
    func doAnimation(){
        
        withAnimation(.spring()){
            
            wish = true
        }
        
        DispatchQueue.main.asyncAfter(deadline: .now() + 3) {
            
            withAnimation(.easeInOut(duration: 1.5)){
                finshWish = true
            }
            
            // Resetting After Wish Finished...
            DispatchQueue.main.asyncAfter(deadline: .now() + 1.5) {
                
                finshWish = false
                wish = false
            }
        }
    }
}

// Global Function for getting Size...
func getRect()->CGRect{
    return UIScreen.main.bounds
}

// Emit Particle View...
// AKA CAEmmiterLayer from UIKit...
struct EmitterView: UIViewRepresentable {
    
    func makeUIView(context: Context) -> UIView {
        
        let view = UIView()
        view.backgroundColor = .clear
        
        // Emitter Layer...
        let emitterLayer = CAEmitterLayer()
        // Since we need top to down animation....
        // it;s your Own Wish...
        // Just change and play with properties.....
        emitterLayer.emitterShape = .line
        emitterLayer.emitterCells = createEmiterCells()
        
        // Size And Postion...
        emitterLayer.emitterSize = CGSize(width: getRect().width, height: 1)
        emitterLayer.emitterPosition = CGPoint(x: getRect().width / 2, y: 0)
        
        view.layer.addSublayer(emitterLayer)
        
        return view
    }
    
    func updateUIView(_ uiView: UIView, context: Context) {
        
    }
    
    func createEmiterCells()->[CAEmitterCell]{
        
        // Multiple Differect Shped Emmiters....
        
        var emitterCells: [CAEmitterCell] = []
        
        for index in 1...12{
            
            let cell = CAEmitterCell()
            
            // Import White Particle Images...
            // Other wise color wont Work....
            cell.contents = UIImage(named: getImage(index: index))?.cgImage
            cell.color = getColor().cgColor
            // New Partcle Creation...
            cell.birthRate = 4.5
            // Particle Existence....
            cell.lifetime = 20
            // Velocity...
            cell.velocity = 120
            // Scale..
            cell.scale = 0.2
            cell.scaleRange = 0.3
            cell.emissionLongitude = .pi
            cell.emissionRange = 0.5
            cell.spin = 3.5
            cell.spinRange = 1
            
            // Accleartion...
            cell.yAcceleration = 40
            
            emitterCells.append(cell)
        }
        
        return emitterCells
    }
    
    func getColor() -> UIColor{
        let colors : [UIColor] = [.systemPink,.systemGreen,.systemRed,.systemOrange,.systemPurple]
        
        return colors.randomElement()!
    }
    
    func getImage(index: Int)->String{
        
        if index < 4{
            return "rectangle"
        }
        else if index > 5 && index <= 8{
            return "circle"
        }
        else{
            return "triangle"
        }
    }
}
```


## Widgets

```
https://developer.apple.com/forums/thread/652198
```


<a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Programming%20languages/Swift/SwiftUI/HOWTO.md#welcome-to-swiftui-howto">Table of contents</a>
