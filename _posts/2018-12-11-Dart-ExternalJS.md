---
layout: post
title: Use External Javascript Libraries for Dart in 4 Steps
tags: [Dart, Javascript, Library, External Library]
excerpt_separator: <!--more-->
---

Hello,  
Today I'm going to show you how to use external Javascript libraries in Dart.  
When you the capabilities of Dart is not enough for you, you may want to use external libraries or you just want to use a specific function of the Javascript.  
At the end of this post, you will learn how to use external libraries and how to port them in Dart.
<!--more-->



## Step 1
First of all, create a blank app using Webstorm's generator.
After that, define the dependency in the pubspec.yaml as 


```yaml
dependencies:
  ...
  js: ^0.6.0
```
After that we update the dependency by using "pub get" command. If you are using Webstorm,
it warns you to update.

> When you create a blank app, you will confront with only one dart file
which is main.dart. If you want to use a new library in this project you will
need a second file that is related with the external library.
So, create a new dart file and name it as you wish.

## Step 2
In that file, you need to use the @JS annotation to set 
the context, say that we are dealing with console and since that file 
will be a library you should use library declaration.

```dart
@JS('console')
library nameasyouwish;
```

following that, you should import the javascript library of the dart;

```dart
import 'package:js/js.dart';
```

The import and library directives can help you to create a modular and 
sharable code base.
We should avare that, every Dart app is a library, even if it 
doesn't use a library directive.
[reference] https://www.dartlang.org/guides/language/language-tour#libraries-and-visibility

## Step 3

After all these, we are now ready to use functions of console, define the functions which are deserved;

```dart
external void log (dynamic str);
external void error(dynamic parameter);
external void clear();

```

The final version of the file will be look like;

```dart
@JS('console')
library myJsConsole

import 'package:js/js.dart';
external void log (dynamic str);
external void error(dynamic parameter);
external void clear();

```
## Step 4

import your library from the main file and call the deserved functions;

```dart
import 'nameOftheFile.dart';

void main() {
    log("Hello World");
    clear();
    error("Hello World is deleted but I'm alive");
}
```
> After that, run the code with the "webdev serve" command and open localhost:8080 in the browser, than open the console with F12.

You will see something like that;  

![Picture](/assets/img/AngularExternalJS.png)





