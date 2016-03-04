## PQActionSheet
######仿微信的ActionSheet，比UIActionSheet用法更简便。

[![CI Status](http://img.shields.io/travis/docee/PQActionSheet.svg?style=flat)](https://travis-ci.org/docee/PQActionSheet)
[![Version](https://img.shields.io/cocoapods/v/PQActionSheet.svg?style=flat)](http://cocoapods.org/pods/PQActionSheet)
[![License](https://img.shields.io/cocoapods/l/PQActionSheet.svg?style=flat)](http://cocoapods.org/pods/PQActionSheet)
[![Platform](https://img.shields.io/cocoapods/p/PQActionSheet.svg?style=flat)](http://cocoapods.org/pods/PQActionSheet)

---------------

##Screenshot

![screenshot](Screenshot/screenshot.gif)


##Installation Guide
**你可以将此代码 `pod 'PQActionSheet', '~> 0.1.2' `贴到你的Podfile文件下，如下所示：**

```
target 'MyApp' do
  pod 'PQActionSheet', '~> 0.1.2'
end

```
在你项目所在目录下执行`pod install` 即可！

##API

**PQActionSheet提供了delegate方式和block方式回调结果，这两种方式对应了两种构造方法，他们分别是：**

```
/**
 *  @brief 初始化PQActionSheet
 *
 *  @param title                  ActionSheet标题
 *  @param delegate               委托
 *  @param cancelButtonTitle      取消按钮标题
 *  @param otherButtonTitles      其他按钮标题
 *
 *  @return PQActionSheet
 */
- (instancetype)initWithTitle:(NSString *)title
                     delegate:(id<PQActionSheetDelegate>)delegate
            cancelButtonTitle:(NSString *)cancelButtonTitle
            otherButtonTitles:(NSString *)otherButtonTitles, ...;
```

```
/**
 *  @brief 初始化PQActionSheet(Block回调结果)
 *
 *  @param title             ActionSheet标题
 *  @param block             Block回调选中的Index
 *  @param cancelButtonTitle 取消按钮标题
 *  @param otherButtonTitles 其他按钮标题
 *
 *  @return PQActionSheet
 */
- (instancetype)initWithTitle:(NSString *)title
               clickedAtIndex:(ClickedIndexBlock)block
            cancelButtonTitle:(NSString *)cancelButtonTitle
            otherButtonTitles:(NSString *)otherButtonTitles, ...;
            
```

由于PQActionSheet是将视图插到UIWindow下面，所以你不用调用addSubview，只需执行`show`方法即可显示。

```
/**
 *  @brief 显示ActionSheet
 */
- (void)show;
```

##License

#####The MIT License (MIT)

######Copyright (c) 2016 <docee>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.