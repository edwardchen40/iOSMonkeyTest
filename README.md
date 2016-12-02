# MonkeyUITesting (fork from ChaosUITesting)

You will need:

* Add new schemes (iCHEFMonkeytest)
<img src="http://i68.tinypic.com/whz8yc.png" />

* Xcode >7.2
* iOS >9.0 simulator
* A working iOS app project
* Install Scan and Sanpshot (Fastlane Toolchain)

## Setup Instructions

**TL;DR:** Add a UI testing target to your Xcode project and import the `MonkeyUITest.swift` file from this repository.

1. Open your Xcode project
2. Go to *File* > *New* > *Target...*
3. Select *iOS* > *Test*
4. Select *iOS UI Testing Bundle*
5. Click *Next*
5. Name your UI tests something like *MonkeyUITests*
6. Click *Finish*
7. Replace the automatically generated tests file with the `MonkeyUITest.swift` file from this repository.

## Initiating MonkeyUITest

You can run the tests by viewing the `MonkeyUITest.swift` file and clicking the little play button next to the class declaration or test method declarations:

<img src="http://i66.tinypic.com/1htrlz.png" />

Or you can run the tests by opening the Test navigator in the Navigator pane on the left of Xcode and clicking the little play button next to the *MonkeyUITest* target:

<img src="http://i63.tinypic.com/121abt0.png" />

There are two tests; one which tests for a set amount of time and one which keeps going until a certain number of gestures has been executed.

To customise the tests, you can change some of the constants declared at the top of the MonkeyUITest class.

### Duration

```swift
let duration: Double = 60 * 3 // Execution time limit in seconds
```

Duration is set to three minutes by default. You can customise the duration with any `Double` value.

### Gesture Limit

```swift
let gestureLimit = 100 // Number of gestures to be executed
```

The gesture limit is set to 100 by default. You can set this number equal to any positive valid unsigned integer value.

### Minimum Gesture Frequency

```swift
let minimumGestureFrequency: UInt32 = 1 // Minimum amount of time to pass between gestures in seconds
```

The minimum frequency of gestures has been set to 1 second by default. Shorter times were tested using `usleep(UInt32)`, but these proved to be unstable.

You can make this integer higher if desired, but things are going to happen pretty slowly if it's increased.

## Provide founction for getting memory usage
```swift
func mach_task_self() -> task_t {
       ...
    }
    
    func getMegabytesUsed() -> Float? {
       ...
    }
```
