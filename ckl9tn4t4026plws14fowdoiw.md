## Developing Cross-Platform Applications using Flutter

The hotshots at Google decided to enter the arena of cross-platform development after mobile frameworks such as [Ionic](https://ionicframework.com/), [React Native](https://reactnative.dev/), and [Xamarin](https://visualstudio.microsoft.com/xamarin/) turned out well. 

From a business perspective, cross-platform apps offer the possibility to significantly reduce the development time and cost. You may think that you need to hire different software development teams to develop your app for different platforms using native solutions. But with cross-platform frameworks, you can create only one code that runs on all, and you wouldn’t have to worry about making different codebases. 

Not only does this mean that you save time, but also cut your costs in half (at the least).  This impacts both, the company's bottom line and time-to-market for their product.

Hence came a framework that supports app development on multiple platforms using a single codebase.

# Introduction
> [Flutter](https://flutter.dev) is Google’s UI toolkit for building beautiful, natively compiled applications for mobile, web, and desktop from a single codebase. 

It is an open-source SDK, primarily developed and sponsored by Google. It uses [Dart](https://dart.dev/) as a programming language, ensuring a single codebase for your project. Dart is a modern, [object-oriented programming](https://www.freecodecamp.org/news/object-oriented-programming-concepts-21bb035f7260/) language, created by Google and has been around since 2011. 

Officially introduced by Google in Feb 2018 as a freely available open-source UI toolkit, Flutter has been growing since, attracting a developers’ community and companies interested in the rapid development of their apps.

> As of March 3, 2021, Flutter supports development on Windows, Mac, Linux, Web, iOS, and Android operating systems.

# Design Systems Suited for Different Environments
The same codebase doesn't really mean that you lose any choice of personalization. This is possible because Flutter has a method that recognizes which operating system it is running on and with some conditions you can choose what you want to display. 

There are two different design systems available in Flutter: 
1. Cupertino, and 
2. Material Design. 

![Artboard – 1.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1614970507751/FhIP1i78-.png)
 
Cupertino is made for iOS style, while Material is Google's design philosophy for android apps and beyond.

# How Flutter works?
### Widgets
**Widgets** are the building blocks of a Flutter app’s user interface. These are the elements inside the code that (like classes) describe how the final interface of the application should look like. Widgets in Flutter can be texts, images, or more complex components. They can be easily composed, combined, and embedded inside each other, without the need to assign attributes. 

In fact, 
> Every single thing you see rendered in the UI, it's all widgets. 

Typically, widgets are composed of many other small, single-purpose widgets that combine to produce powerful effects. For example, to center a piece of text, you put the text in a **Text** widget and wrap it in a **Center** widget.
```dart
Center(
    child : Text("Hello World!");
);
```
This allows for a Declarative/Reactive approach to making user interfaces (rather than an imperative approach), which greatly speeds up the development process. 

### Full Control over Every Pixel
In traditional Android apps, the system libraries provide the components responsible for drawing themselves to a Canvas object, which Android can then render with [Skia](https://skia.org/), a graphics engine written in C/C++ that calls the CPU or GPU to paint the UI on the device.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1613505595988/O5x0RjtZD.png)

A typical *Cross-Platform framework* creates an abstraction layer over the underlying native Android and iOS UI libraries. The code in which the App is often written is used to interact with Android(*Java*) or iOS(*Objective-C*) system libraries to display UI.

Flutter bypasses all these abstractions by using **its own set of Widgets** (including Google's Material design and iOS' Cupertino widgets). 
> That’s right, **Flutter does not use the OEM widgets (or DOM WebViews), it provides its own widgets.**

The Dart code used by Flutter apps to paint the UI is directly compiled into native code "Ahead of Time" (AoT) using **Flutter's own copy of Skia** as part of its rendering engine.

This allows developers to equip their apps with the latest performance improvements even if the operating system running them is not the latest version. This is true for every platform which Flutter apps run on including macOS, Windows, Android, and iOS.

Here's a brief overview of how Flutter works:

![0_cB99P1pYqNWONq7Q.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1613508127409/TDwJWZODg.png)
The Flutter portion of the app sends messages to its host, the iOS or Android portion of the app, over a **platform channel**. The host listens on the platform channel and receives the message. It then calls the platform-specific APIs and sends a response back to the client, the Flutter portion of the app. These messages and responses are passed intermittently, to ensure the user interface remains responsive.
> All that Flutter requires of the platform is a canvas in which to render the widgets so they can appear on the device screen, and access events (touches, timers, etc.) and services (location, camera, etc.).

# Why Flutter Rocks?
- ### Hot Reload
If you ask any of Flutter app developers what their favorite part of Flutter is, they'll say it's **Hot Reload**. 
![image.png](https://hackernoon.com/hn-images/1*c1dM9uhkRj9_fpiDrLJmDw.gif)
The experience is like painting a picture. You can simultaneously modify your code and hit save, and almost instantly, like magic, it’s all updated on your screen. This is because Flutter doesn’t build the whole screen over again, it only updates what is different in your code. Flutter uses a JIT compiler that can reload and continue executing code usually in under a second. It implements the change in your UI without reloading the whole app or messing with inputs and variables.

- ### Independence from Platform Updates
Flutter apps are separated from all native components of OS. Even if Android or iOS updates its controls, the apps will retain their appearance and functionality.

- ### Open-Source
Flutter is open-source. It is continuously being developed by the community. Moreover, despite the open-source distribution, Google strongly supports this technology, consistently updating the framework. The best part is that its development is driven dominantly by the developers' community.

- ### Fast programming
Flutter needs to create and destroy a multitude of short-lived objects very fast. Dart’s ‘garbage collection’ is well suited for this purpose, and it is reflected in the performance of the apps. **Dart** is a very simple language to learn and I doubt it'll stop you from trying out Flutter. Consider this simple class written in Dart:
```dart
class Book {
    final String title;
    final double price;
    int noOfCopies;
    
    Book(this.title, this.price, this.noOfCopies);

    void rentOut() {
        noOfCopies--;
    }

    void deposit() {
        noOfCopies++;
    }
}
```
See for yourself. Its syntax is similar to most Object-Oriented Languages. Of course, there is some language-specific syntactical sugar, and you can start writing code that is more inherent once you learn the language, but the point is that the **learning curve is rather small**. The Flutter team had a good reason to choose it as its foundational programming language. Read about it [here](https://flutter.dev/docs/resources/faq#why-did-flutter-choose-to-use-dart).

- ### The Flutter Community
This is perhaps the best thing about Flutter. Despite being the new kid on the block, it has amassed the support of a myriad of developers across the globe in such a short time. There are constant discussions on Flutter-related [discord servers](https://discord.gg/rflutterdev) between newbies and experienced developers every other day. I usually get my queries answered within a couple of hours there. If my questions' length is unsuited for fast-paced conversations, I put it on [StackOverflow](https://stackoverflow.com/questions/tagged/flutter) with the #flutter tag. Their response time is mindblowing.
---

# Learning Resources
- ### Documentation
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1613521206700/VOc9DvKOn.png)
If you have had experience with any of the other programming languages in the past, reading the [official Flutter documentation](https://flutter.dev/docs) is the simplest answer. You will find everything – articles on [how to set up the environment](https://flutter.dev/docs/get-started/install), [Widget catalog](https://flutter.dev/docs/development/ui/widgets) and [API reference](https://api.flutter.dev/). There are also many tutorials and samples that show new developers how to use Flutter API and build beautiful apps in record-breaking time.

- ### The Boring Flutter Development Show
I recommend [The Boring Flutter Development Show](https://www.youtube.com/playlist?list=PLjxrf2q8roU3ahJVrSgAnPjzkpGmL9Czl) for anyone who wants to see real Googlers struggle and learn from their mistakes. A fun way to learn Flutter. The idea behind it is to show everyone that developers are not prodigies or superhumans and that they are as prone to mistakes as we are. This show also helps people from shedding their imposter syndrome. All of this while making stuff using Flutter.

- ### Widget of the Week
A YouTube playlist from Google developers to learn about Flutter widgets. It’s a playlist with short one-minute videos, each one regarding a single widget per video available in the Flutter SDK. I highly recommend you give it a try as it has many great videos to help you discover and learn about Flutter widgets. They launch 1 video every week, hence - [Widget of the Week](https://www.youtube.com/playlist?list=PLjxrf2q8roU23XGwz3Km7sQZFTdB996iG).

- ### Courses
For those who are fans of instructor-led courses, 2 excellent courses come recommended, both of which are suited for newbies and intermediate developers alike: 
 1. Dr. Angela Yu's [The Complete 2021 Flutter Development Bootcamp with Dart](https://www.udemy.com/course/flutter-bootcamp-with-dart/). This one comes recommended by the Flutter team themselves.
 2. Maximilian Schwarzmüller's  -  [Flutter & Dart - The Complete Guide [2021 Edition]](https://www.udemy.com/course/learn-flutter-dart-to-build-ios-android-apps/).

---
With Flutter, you can build almost anything. If you have a cool app idea, like a chat where people can only talk through GIFs, you can use Flutter. If you want to build the next big communication desktop app, like Skype, Flutter is a great option.

With Flutter the possibilities are endless and you can start right now.

#### I hope my article encouraged some of you to try out Flutter for building your apps. If you liked it, consider tweeting it to your network. 

Ciao!