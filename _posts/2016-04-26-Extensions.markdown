---
title:  "Extensions"
date:   2016-04-26
categories: [Extensions]
tags: [Extensions, Swift 2.2, UIColor]
---

Swift extensions are powerful and with a little  bit of help they let you write cool and safe code. An example of this is:

``` swift
extension UIColor {

 enum Colors: Int {
	case Red = 0xEA524B
	case Green = 0x81C73A
 }
    
 convenience public init(hex: Int, alpha: CGFloat = 1.0) {
 	let red = CGFloat((hex & 0xFF0000) >> 16) / 255.0
	let green = CGFloat((hex & 0xFF00) >> 8) / 255.0
	let blue = CGFloat((hex & 0xFF)) / 255.0
	self.init(red: red, green: green, blue: blue, alpha: alpha)
 }
    
 convenience init(color: Colors) {
	self.init(hex: color.rawValue)
 }
 
}
```


This enables us to use UIColor in our code in a much convenience way and centralizes all the information regarding colors on our project. For instance, to change the color on an UIView:

``` swift
view.backgroundColor = UIColor(color: .Red)
```

In my opinion this is an excellent solution and makes your code more concise, explicit and overall more clean.


Hope you enjoyed the post, any questions feel free to reach me on [Twitter](https://twitter.com/DSwifting) ;)




