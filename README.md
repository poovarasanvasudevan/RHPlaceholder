<p align="center">
<img src ="./ReadmeAssets/Logo.gif" width="150" height="150"/>
</p>

[![Version](https://img.shields.io/cocoapods/v/RHPlaceholder.svg?style=flat)](http://cocoadocs.org/docsets/RHPlaceholder)
[![License](https://img.shields.io/cocoapods/l/BadgeSwift.svg?style=flat)](/LICENSE)
[![Platform](http://img.shields.io/badge/platform-ios-blue.svg?style=flat)](https://developer.apple.com/iphone/index.action)
[![Language](http://img.shields.io/badge/language-swift-brightgreen.svg?style=flat)](https://developer.apple.com/swift)

# RHPlaceholder 💾
Because tradicional `loading view` like `UIActivityIndicatorView` or similar one are noo longer so trendy (Facebook or Instagram apps are moving away from these approaches), I decided to create very simple library which will give you oportunity to have Facebook or Instagram 'view loading state' in your great project without big effort 💥! 🍕 

## Play with it 😎


## Installation
You can install library using Cocoapods:
```
pod 'RHPlaceholder'
```

## Usage
WOW... it is soo easy to use 🙊! Base integration with your storyboard VC will take couple minutes 💥

### Base Usage
just create instance const of `Placeholder` in your `ViewController`:
```swift
private let placeholderMarker = Placeholder() // By default you will have Insta like gradient animation
```

bear in mind, that you can choose between couple of predefined animations (like e.g. RainbowAnimatorGradient):
```swift
private let placeholderMarker = Placeholder(layerAnimator: RainbowAnimatorGradient.self)
```

... and then just bind up library with your views which needs to be animated:

```swift
private func addPlaceholder() {
    let viewElements: [UIView] = [
        name,
        surname,
        age,
        email,
        birthDate
    ]
        
    placeholderMarker.register(viewElements)
}
```
call `addPlaceholder()` method in `viewDidLoad()`. 
Boom 😲 library has been associated with your views 👏

all what left, is to controll showing 'loading state' animation on your views using `startAnimation()` and `remove()`
```swift
func fetchUserData() {
    placeholderMarker.startAnimation()
    apiManager.fetchUser() { [weak self] user in 
        self?.placeholderMarker.remove()
        // .. rest of the method
    }
}
```

#### List of available animatotrs: 
##### (`default`) InstaLayerAnimatorGradient
<p align="center">
<img src ="./ReadmeAssets/insta1.gif" width="148" height="285"/>
<img src ="./ReadmeAssets/insta2.gif" width="148" height="285"/>
</p>

##### BackAndFortLayerAnimatorGradient
<p align="center">
<img src ="./ReadmeAssets/bf1.gif" width="148" height="285"/>
<img src ="./ReadmeAssets/bf2.gif" width="148" height="285"/>
</p>

##### BlinkAnimator
<p align="center">
<img src ="./ReadmeAssets/blink1.gif" width="148" height="285"/>
<img src ="./ReadmeAssets/blink2.gif" width="148" height="285"/>
</p>

##### RainbowAnimatorGradient
<p align="center">
<img src ="./ReadmeAssets/Rainbow1.gif" width="148" height="285"/>
<img src ="./ReadmeAssets/rainbow2.gif" width="148" height="285"/>
</p>

### Advanced Configuration
TBC

### Create your own animation! 🙊
TBC

## Swift support
| Library ver| Swift ver| Note |
| ------------- |:-------------:| ------------- |
| 0.0.1   | 4.1 | Very early version, API may change |

## Check the Demo project

Please check out the demo project, you can see there how Library has been implemented in details.

### Layout Inspiration
Layout inspiration has been taken from one of the Dribbble projects, unfortunately I cannot find now this project anymore, because of that I cannot annotate creator in here 😦...

### Assets
---
- Great 😍 tab bar icons from:
<div>Icons made by <a href="http://www.freepik.com" title="Freepik">Freepik</a> from <a href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a> is licensed by <a href="http://creativecommons.org/licenses/by/3.0/" title="Creative Commons BY 3.0" target="_blank">CC 3.0 BY</a></div>

---

- Cool 😎 profile icon from:
<div>Icons made by <a href="http://www.freepik.com" title="Freepik">Freepik</a> from <a href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a> is licensed by <a href="http://creativecommons.org/licenses/by/3.0/" title="Creative Commons BY 3.0" target="_blank">CC 3.0 BY</a></div>


---
## TODO:
- URGENT
- [ ] create pod

- OPTIONAL
- [ ] extract gradient animations logic
- [ ] add posibility to set bg image below animated gradient
- [ ] improve InstaLayerAnimatorGradient, gradient should respect the size of layer in which he is displayed

 
