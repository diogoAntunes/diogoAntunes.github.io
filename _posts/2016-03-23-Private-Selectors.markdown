---
title:  "Private Selectors"
date:   2016-03-23
categories: [Selector]
tags: [Selector, Swift 2.2, Private]
---

Swift 2.2 is out, and with it the new Selectors :)

So instead of:

``` swift
let newButton = UIButton()
newButton.addTarget(nil, 
	action: "selector:", 
	forControlEvents: .TouchUpInside)

func selector(button: UIButton) { }
```

We can now do:

``` swift
newButton.addTarget(nil, 
	action: #selector(selector(_:)),
	forControlEvents: .TouchUpInside)

func selector(button: UIButton) { }
```
Which is awesome! Now we have type-safe selectors that allow in compile time to check for the existence of the Selector. A cool trick you can do is make the selectors only accessible inside the class, by making them private: 

``` swift
newButton.addTarget(nil, 
	action: #selector(privateSelector(_:)),
	forControlEvents: .TouchUpInside)

@objc private func privateSelector() { }
```


