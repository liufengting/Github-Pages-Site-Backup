---

layout:     post
title:      "FTPopOverMenu"
subtitle:   "FTPopOverMenu. A pop over menu which is maybe the easiest to use."
date:       2016-03-04 14:00:00
header-img: "img/macbookpro.jpg"

---

<h1>FTPopOverMenu</h1>

FTPopOverMenu. A pop over menu which is maybe the easiest to use.


<h2>Useage</h2>

```objective-c

    [[FTPopOverMenu sharedInstance] showForSender:sender
                                     withMenu:@[@"MenuOne",@"MenuTwo",@"MenuThr"]
                               imageNameArray:@[@"setting_icon",@"setting_icon",@"setting_icon"]
                                    doneBlock:^(NSInteger selectedIndex) {
                                        NSLog(@"done block. do something. selectedIndex : %ld", (long)selectedIndex);
                                        
                                    } dismissBlock:^{
                                        NSLog(@"user canceled. do nothing.");
                                        
                                    }];

```

<h2>ScreenShots</h2>

<table>
	<tr>
		<th><img src="https://raw.githubusercontent.com/liufengting/FTPopOverMenu/master/ScreenShots/ScreenShot01.jpg" width="400"/></th>
		<th><img src="https://raw.githubusercontent.com/liufengting/FTPopOverMenu/master/ScreenShots/ScreenShot02.jpg" width="400"/></th>
	</tr>
	<tr>
		<th><img src="https://raw.githubusercontent.com/liufengting/FTPopOverMenu/master/ScreenShots/ScreenShot03.jpg" width="400"/></th>
		<th><img src="https://raw.githubusercontent.com/liufengting/FTPopOverMenu/master/ScreenShots/ScreenShot04.jpg" width="400"/></th>
	</tr>
</table>







See More Here: [FTPopOverMenu](https://github.com/liufengting/FTPopOverMenu)


