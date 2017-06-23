# iOS-Summary-Part2

文章大纲，便于浏览

### 1.NSTimer
以下[文章](http://www.jianshu.com/p/330d7310339d)详细讲述了NSTimer的创建、销毁以及与NSRunLoop的关系，通读几遍，就可以融会贯通了


### 2.iOS应用程序间共享数据

这篇[文章](http://www.jianshu.com/p/169e31cacf42)义工介绍了四种应用程序间共享数据的方法

### 3.开源许可说明
![](http://okhqmtd8q.bkt.clouddn.com/image/jpg/%E5%BC%80%E6%BA%90%E8%AE%B8%E5%8F%AF%E8%AF%B4%E6%98%8E.jpg)



### 4.枚举的三种写法


* 普通写法

```objc
typedef enum
{
    GZQDemoTypeTop,
    GZQDemoTypeBottom,
}GZQDemoType;

```

* 文艺写法

```objc
定义类型
typedef NS_ENUM(NSInteger,GZQType)
{
    GZQTypeTop,
    GZQTypeBottom,
};

```

* 推荐写法（可以进行位运算，更加灵活）

```objc

typedef NS_OPTIONS(NSInteger, GZQActionType)
{
    GZQActionTypeA = 1<<0,
    GZQActionTypeb = 1<<1,
    GZQActionTypec = 1<<2,
    GZQActionTypeD = 1<<3,
}
```

### 5.didReceiveMemoryWarning
当系统内存告急时，会接收到`didReceiveMemoryWarning`。
这是属于`ViewController`的方法，当`ViewController`接收到`didReceiveMemoryWarning`，首先会判断当前的`ViewController`是否还显示在`window`上，如果不在就会移除当前的`ViewController`，销毁`ViewController`上面的子控件，并执行`ViewDidUnload`方法

具体参考下图：

![](http://okhqmtd8q.bkt.clouddn.com/image/jpg/MemoryWarning.png)

    



