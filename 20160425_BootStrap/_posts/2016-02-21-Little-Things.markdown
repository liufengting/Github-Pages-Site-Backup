---

layout:     post
title:      "Little Things"
subtitle:   "Little Things To Remember..."
date:       2016-02-21 14:00:00
header-img: "img/macbookpro.jpg"

---


<h1>OSX el Capitan gem update error</h1>

* OSX el Capitan gem update error

```
sudo gem install -n /usr/local/bin GEM_NAME_HERE
```


<h1>不规则图片</h1>

_maskLayer = [CAShapeLayer layer];
 _maskLayer.fillColor = [UIColor blackColor].CGColor; _maskLayer.strokeColor = [UIColor clearColor].CGColor; _maskLayer.frame = self.bounds;
 _maskLayer.contentsCenter = CGRectMake(0.5, 0.5, 0.1, 0.1); _maskLayer.contentsScale = [UIScreen mainScreen].scale; //非常关键设置自动拉伸的效果且不变形 
_maskLayer.contents = (id)[UIImage imageNamed:@"gray_bubble_right@2x.png"].CGImage; _contentLayer = [CALayer layer]; _contentLayer.mask = _maskLayer; _contentLayer.frame = self.bounds; [self.layer addSublayer:_contentLayer];

<h1>iOS NavigationBar 透明</h1>

OC

[self.navigationController.navigationBar setBackgroundImage:[UIImage new] forBarMetrics:UIBarMetricsDefault];
[self.navigationController.navigationBar setShadowImage:[UIImage new]];
[self.navigationController.navigationBar setTranslucent:YES];

Swift

self.navigationController?.navigationBar.setBackgroundImage(UIImage(),forBarMetrics: UIBarMetrics.Default)
self.navigationController?.navigationBar.shadowImage = UIImage()
self.navigationController?.navigationBar.translucent = true


<h1>GithubPages</h1>

rm Gemfile.lock

bundle install    

bundle exec jekyll serve 

git add --a    

git commit -m "Edit something"

git push 

<h1>UIView转成UIImage</h1>
、、、swift

    private func getImageFromView(view : UIView) -> UIImage {
        UIGraphicsBeginImageContextWithOptions(view.bounds.size, true, 2)
        view.layer.renderInContext(UIGraphicsGetCurrentContext()!)
        let image : UIImage = UIGraphicsGetImageFromCurrentImageContext();
        UIGraphicsEndImageContext();
        return image;
    }
    private func getAnimationFrameForImage(image : UIImage?) -> CGRect{
        
        if (image == nil) {
            return CGRectZero
        }
        let imageSize = image!.size
        let aspect = imageSize.width / imageSize.height
        var animationFrame = CGRectZero;
        if (FTImageViewerScreenWidth / aspect <= FTImageViewerScreenHeight) {
            animationFrame.size = CGSizeMake(FTImageViewerScreenWidth, FTImageViewerScreenWidth / aspect)
        }else {
            animationFrame.size = CGSizeMake(FTImageViewerScreenHeight * aspect, FTImageViewerScreenHeight);
        }
        animationFrame.origin.x = (FTImageViewerScreenWidth - animationFrame.size.width)/2.0
        animationFrame.origin.y = (FTImageViewerScreenHeight - animationFrame.size.height)/2.0
        return animationFrame;
    }
    
、、、

<h1>判断点击事件是否在某个范围内</h1>

、、、objective-c


-(void)onBackgroundViewTapped:(UIGestureRecognizer *)gesture
{
    if (CGRectContainsPoint(_popMenuView.frame, [gesture locationInView:_backgroundView])) {
        NSLog(@"touch in subview");
    }else{
        [self dismiss];
    }
}

、、、


<h1>SQL排序</h1>

// Events sorted by date, defaults to ascending
var events = Event.all(sort: "when") as! [Event]
// Descending
var descendingEvents = Event.all(sort:["when":"DESC"]) as! [Event]
// or
var descEvents = Event.all(sort:"when DESC, eventID ASC")

// All meeting events sorted by when desc and eventID ascending and limit 10
var theseEvents = Event.query(["type":"meeting"], sort:["when":"DESC","eventID":"ASC"], limit: 10) as! [Event]

// NSSortDescriptor as sort arg (or array of NSSortDescriptors
Event.all(sort: NSSortDescriptor(key:"when",ascending:true))

