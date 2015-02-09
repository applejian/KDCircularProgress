# KDCircularProgress
`KDCircularProgress` is a circular progress view written in Swift. It makes it possible to have gradients in the progress view, along with glows and animations. Here's an example

[![Screenshot](https://raw.githubusercontent.com/kaandedeoglu/KDCircularProgress/master/screenshot.png)](http://youtu.be/iIdas72MXOg)

```swift
        let progress = KDCircularProgress(frame: CGRect(x: 0, y: 0, width: 300, height: 300))
        progress.startAngle = -90
        progress.progressThickness = 0.2
        progress.trackThickness = 0.7
        progress.clockwise = true
        progress.center = view.center
        progress.gradientRotateSpeed = 2
        progress.roundedCorners = true
        progress.glowMode = .Forward
        progress.angle = 300
        progress.setColors(UIColor.cyanColor() ,UIColor.whiteColor(), UIColor.magentaColor())
        view.addSubview(progress)
```

## Installation

- Just drag `KDCircularProgress.swift` into your project. `Carthage` support is on To-do list.

## Properties

####angle: `Int`
The angle of the progress. Between 0 and 360 (inclusive). Simply change its value in order to change the visual progress of the component. Default is 0.

####startAngle: `Int`
The angle at which the progress will begin. Between 0 and 360 (inclusive), however you can pass any negative or positive values and the component will mod them automatically to the required range. Default is 0.

####clockwise: `Bool`
Clockwise if true, Counter-clockwise if false. Default is true.

####roundedCorners: `Bool`
When true, the ends of the progress track will be drawn with a half circle radius. Default is false.

####gradientRotateSpeed: `CGFloat`
Describes how many times the underlying gradient will turn for each full cycle of the progress. Integer values recommended. Default is 0.

####glowAmount: `CGFloat`
The intensity of the glow. Between 0 and 1.0. Default is 1.0.

####glowMode: `KDCircularProgressGlowMode`
- **.Forward** - The glow increases proportionaly to the angle. No glow at 0 degrees and full glow at 360 degrees.

- **.Reverse** - The glow increases inversely proportional to the angle. Full glow at 0 degrees and no glow at 360 degrees.

- **.Constant** - Constant glow.

- **.None** - No glow

The default is **.Forward**

####progressThickness: `CGFloat`
The thickness of the progress. Between 0 and 1. Default is 0.4

####trackThickness: `CGFloat`
The thickness of the background track. Between 0 and 1. Default is 0.5

####trackColor: `UIColor`
The color of the background track. Default is black.

####progressColors: `[UIColor]`
The colors used to generate the gradient of the progress. You can also set this using the variadic setColors(UIColor...) method. A gradient is used only if there is more than one color. A fill is used otherwise. The default is a white fill.

##Methods
```swift 
override public init(frame: CGRect)
```
Initialize with a frame. Please only use square frames.

```swift 
convenience public init(frame:CGRect, colors: UIColor...)
```
Initialize with a frame and the gradient colors.

```swift 
public func setColors(colors: UIColor...)
```

Set the colors for the progress gradient.

```swift
public func animateFromAngle(fromAngle: Int, toAngle: Int, duration: NSTimeInterval, completion: ((Bool) -> Void)?)
```

Animate the progress from an initial value to a final value, with a completion block that fires after the animation is done.

```swift
public func animateToAngle(toAngle: Int, duration: NSTimeInterval, completion: ((Bool) -> Void)?)
```

Animate the progress from the current state to a target value.

```
swift public func pauseAnimation()
```

Pause the animation, if any.

```
swift public func isAnimating() -> Bool
```

Check if there's an active animation.

##Misc
Prefering light colors in the gradients gives better results. As mentioned before, use square frames. Rectangular frames are not tested and might produce unexpected results.

##To-Do
- [ ] Carthage Support
- [ ] IBDesignable/IBInspectable support
- [ ] Adding a `progress` property as an alternative to `angle`
- [ ] Clean up

##Contact
Drop me an email if you want discuss anything further.

[Email](kaandedeoglu@me.com)

##License

The MIT License (MIT)

Copyright (c) 2015 Kaan Dedeoglu

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.