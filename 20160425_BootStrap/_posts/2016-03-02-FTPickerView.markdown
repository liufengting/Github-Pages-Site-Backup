---

layout:     post
title:      "FTPickerView"
subtitle:   "A simple UIPickerView/UIDatePicker wapper."
date:       2016-03-02 14:00:00
header-img: "img/macbookpro.jpg"

---


<h1>FTPickerView</h1>

A simple UIPickerView/UIDatePicker wapper. Easy to use.

<h2>Features</h2>

* singleton
* block callbacks


<h1>Simple Picker</h1>

![FTPickerView Simple Picker](https://raw.githubusercontent.com/liufengting/FTPickerView/master/ImageAssets/SimplePicker.png)


<h2>Useage</h2>

```objective-c

//simple picker
NSArry *nameArray = @[@"optionA",@"optionB",@"some other option"]
[[FTPickerView sharedInstance]  showWithTitle:@"i am title"
                                    nameArray:nameArray
                                    doneBlock:^(NSInteger selectedIndex) {
                                       		NSLog(@"the selected string is: %@",nameArray[selectedIndex]);
                                    } cancelBlock:^{
                                    }];
```

<h1>Date Picker</h1>

![FTPickerView Simple Picker](https://raw.githubusercontent.com/liufengting/FTPickerView/master/ImageAssets/DatePicker.png)

<h2>Useage</h2>

```objective-c

//date picker
[[FTDatePickerView sharedInstance] showWithTitle:@"选择日期"
                                      selectDate:[NSDate date]
                                  datePickerMode:UIDatePickerModeDateAndTime
                                       doneBlock:^(NSDate *selectedDate) {
                                            NSDateFormatter *f = [[NSDateFormatter alloc]init];
                                            [f setDateFormat:@"yyyy年MM月dd日 HH:mm:ss"];
                                            NSLog(@"the selected date is: %@",[f stringFromDate:selectedDate]);
                                  } cancelBlock:^{
                                  }];
```

<h1>Installation</h1>

Drag 'FTPickerView' file to you project,
Import 'FTPickerView.h',
Enjoy！ 🍺

View detial at : [FTPickerView](http://liufengting.github.io/FTPickerView)