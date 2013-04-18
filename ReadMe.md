##Overview
`CNSplitView` is an feature enhanced derivative of `NSSplitView`. It has support for sticky top or bottom toolbars for each of its subviews. You can configure `CNSplitView` to add toolbars with buttons and/or drag handles, you can define the orientation of each button inside the toolbar or center it all.


Here are two shots of the included example application:

![CNSplitView Example - Vertical SplitView](https://dl.dropbox.com/u/34133216/WebImages/Github/CNSplitView-Vertical-Example.png)

![CNSplitView Example - Horizontal SplitView](https://dl.dropbox.com/u/34133216/WebImages/Github/CNSplitView-Horizontal-Example.png)


##Graphics & Icons
The icon used to show in the example application (green leaf) was taken from [IconFinder](http://www.iconfinder.com/icondetails/35391/256/garden_green_leaf_nature_organic_plant_icon). It is published under the [CC License Attribution-Noncommercial 3.0](http://creativecommons.org/licenses/by-nc/3.0/) and was created by [Bruno Maia, IconTexto](http://www.icontexto.com).

##Installation
####Via CocoaPods
Just add `pod 'CNSplitView'` to your podfile.

####Via Git SubModule
`cd` into your project directory and execute `git submodule add https://github.com/phranck/CNSplitView.git $DIR_WHERE_YOUR_SUBMODULES_ARE_PLACED`

You have to replace the `$DIR_WHERE_YOUR_SUBMODULES_ARE_PLACED` with the real path where your submodules are placed.

####Manually
Download the entire project from Github via `git clone https://github.com/phranck/CNSplitView.git`, `cd` into the `CNSplitView` directory and drag the underyling `CNSplitView` directory to your Xcode project.


##Usage
The usage of `CNSplitView` is quite simple. In Interfacebuilder just create a new window, grab a `NSSplitView` from the objects palette and drop it onto the content view of your window. Select the the size inspector and let it fill the container both horizontally and vertically. Then you select the identity inspector and set the class of this `NSSplitView` to `CNSplitView`. In Interfacebuilder you're done for that moment.

On the code side you keep going that easy way. The code of the example application looks like this:

```Objective-C
CNSplitViewToolbarButton *button1 = [[CNSplitViewToolbarButton alloc] init];
button1.imageTemplate = CNSplitViewToolbarButtonImageTemplateAdd;
button1.keyEquivalent = @"n";
button1.keyEquivalentModifierMask = NSCommandKeyMask;

CNSplitViewToolbarButton *button2 = [[CNSplitViewToolbarButton alloc] init];
button2.imageTemplate = CNSplitViewToolbarButtonImageTemplateRemove;

CNSplitViewToolbarButton *button3 = [[CNSplitViewToolbarButton alloc] init];
button3.imageTemplate = CNSplitViewToolbarButtonImageTemplateLockUnlocked;
button3.imagePosition = NSImageRight;
button3.title = @"Lock";

CNSplitViewToolbarButton *button4 = [[CNSplitViewToolbarButton alloc] init];
button4.imageTemplate = CNSplitViewToolbarButtonImageTemplateRefresh;
button4.title = @"Refresh";

// NSTextField *textField = [[NSTextField alloc] init];
// [textField setBezeled:YES];
// [textField setBezeled:NSTextFieldRoundedBezel];
// [textField setToolbarItemWidth:120.0];

NSPopUpButton *popupButton = [[NSPopUpButton alloc] init];
[popupButton setToolbarItemWidth:120];
[popupButton addItemsWithTitles:@[ @"Foo...", @"Bar...", @"Yelly" ]];
[[popupButton cell] setControlSize:NSSmallControlSize];

// NSSlider *slider = [[NSSlider alloc] init];
// [slider setToolbarItemWidth:120.0];
// [[slider cell] setControlSize:NSSmallControlSize];

[toolbar addItem:button1 align:CNSplitViewToolbarItemAlignLeft];
[toolbar addItem:button2 align:CNSplitViewToolbarItemAlignLeft];
[toolbar addItem:button3 align:CNSplitViewToolbarItemAlignRight];
[toolbar addItem:button4 align:CNSplitViewToolbarItemAlignRight];
[toolbar addItem:popupButton align:CNSplitViewToolbarItemAlignLeft];

self.splitView.delegate = self;
self.splitView.toolbarDelegate = self;
[self.splitView attachToolbar:toolbar toSubViewAtIndex:0 onEdge:CNSplitViewToolbarEdgeBottom];
```


##Requirements
`CNSplitView` was written using ARC and should run on 10.7 and above. Also you have to add the QuartzCore Framework to your project.


##Contribution
The code is provided as-is, and it is far off being complete or free of bugs. If you like this component feel free to support it. Make changes related to your needs, extend it or just use it in your own project. Feedbacks are very welcome. Just contact me at [opensource@cocoanaut.com](mailto:opensource@cocoanaut.com?Subject=[CNSplitView] Your component on Github), send me a ping on **Twitter** [@TheCocoaNaut](http://twitter.com/TheCocoaNaut) or **App.net** [@phranck](https://alpha.app.net/phranck). 


##Documentation
The documentation of this project is auto generated using [Appledoc](http://gentlebytes.com/appledoc/) by [@gentlebytes](https://twitter.com/gentlebytes).<br />
You can find the complete reference [here](http://CNSplitView.cocoanaut.com/documentation/).


##License
This software is published under the [MIT License](http://cocoanaut.mit-license.org).
