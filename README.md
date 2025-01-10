# Objective-C KVO Crash Bug

This repository demonstrates a common, yet subtle, bug in Objective-C related to Key-Value Observing (KVO). The bug occurs when an observer is not removed from the observed object before the object is deallocated.  This results in a crash due to accessing deallocated memory.

## Bug Description
The `bug.m` file contains code that showcases the problematic situation.  An observer is added to an object, and the object is later deallocated without removing the observer. This leads to an `EXC_BAD_ACCESS` crash.

## Solution
The `bugSolution.m` file provides a corrected version. The solution is to ensure the observer is removed using `removeObserver:` before the observed object is deallocated. Proper memory management practices and using blocks for observing can help to mitigate this issue further.  Refer to Apple's documentation for best practices concerning KVO.

## How to Reproduce
1. Clone this repository.
2. Open the project in Xcode.
3. Run the application. Observe the crash in `bug.m` and the correct behaviour in `bugSolution.m`.