# ELFoundation [![Build Status](https://travis-ci.org/Electrode-iOS/ELFoundation.svg?branch=master)](https://travis-ci.org/Electrode-iOS/ELFoundation)

ELFoundation is a Swift framework that provides a base layer of functionality for Electrode-iOS modules and applications such as helper extensions, utility classes, and other generic constructs.

## Requirements

ELFoundation requires Swift 2.1 and Xcode 7.2.

## Installation

Install by adding `ELFoundation.xcodeproj` to your project and configuring your target to link `ELFoundation.framework`.

## Usage

Numerous methods all over the source. Please see the code for up to date documentation. Following is a brief overview:

* `exceptionFailure` - A replacement for assertionFailure, usable in tests.
* `synchronized<T>` - Akin to @synchronized() in Objective-C.
* `Spinlock` - A basic spinlock implementation for synchronization.
* `Object Association` - Objective-C style object association.
* `Swizzling` - Objective-C style swizzling.
* `String (extensions)` - Handy extensions.
* `Array (extensions)` - Handy extensions.
* `NSObject (extensions)` - Handy extensions.
* `NSThread (extensions)` - Handy extensions.
* `NSError (extensions)` - Handy extensions.
* `NSBundle (extensions)` - Handy extensions.
* `XCTestCase (extensions)` - Gets XCTAssertThrows working in Swift.

## Some Examples

Synchronized property access:

```Swift
public var suspended: Bool {
    get {
        return lock.around {
            self.suspended
        }
    }
    
    set(value) {
        lock.around {
            self.suspended = value
        }
    }
}
```

More to come...

## Contributions

We appreciate your contributions to all of our projects and look forward to interacting with you via Pull Requests, the issue tracker, via Twitter, etc.  We're happy to help you, and to have you help us.  We'll strive to answer every PR and issue and be very transparent in what we do.

When contributing code, please refer to our Dennis (https://github.com/Electrode-iOS/Dennis).

## License

The MIT License (MIT)

Copyright (c) 2015 Walmart

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
