# Inconsistent Deep Link Handling with Expo Linking API

This repository demonstrates a bug related to inconsistent deep link handling in the Expo `Linking` API.  The issue occurs when using `Linking.addEventListener` to listen for deep links. Under certain circumstances, the event listener might fail to fire consistently, leading to missed deep links. This is often more pronounced in background processing, state changes, or specific device configurations.

The included example shows a basic implementation of deep linking and demonstrates how to work around the inconsistencies. The solution involves more robust error handling and checking for deep links on app startup and app state changes. 

## Bug Reproduction Steps

1. Clone the repository.
2. Run `npm install` to install the dependencies.
3. Start the app in Expo Go.
4. Attempt to open a deep link. Note that the deep link may not be handled consistently.  Try changing device state (background/foreground) or triggering more deep links in quick succession to see irregular behavior.

## Solution

The solution file demonstrates an improved approach to deep link handling, implementing mechanisms to increase the chances of capturing links. This usually involves checking for deep links at app start, in the foreground, and handling potential edge cases of listeners not firing immediately.
