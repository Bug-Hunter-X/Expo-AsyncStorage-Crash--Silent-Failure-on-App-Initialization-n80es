# Expo AsyncStorage Crash: Silent Failure on App Initialization

This repository demonstrates a common yet frustrating bug in Expo apps involving AsyncStorage: the app crashes silently without providing any useful error messages in the console. This typically happens when AsyncStorage is accessed before the app's environment is fully set up.

## Bug Description

The core problem is attempting to read or write to AsyncStorage too early in the app's lifecycle, usually within a component's `useEffect` hook before AsyncStorage is ready.  This results in a crash, leaving developers puzzled and without clear error indicators.

## Reproduction

1. Clone this repository.
2. Run `npm install`.
3. Run the app on an emulator or physical device.
4. Observe the silent crash.  No meaningful error messages will be present in the console.

## Solution

The solution involves adding a check to ensure AsyncStorage is available before attempting any operations.  This is demonstrated in `bugSolution.js`.

## Additional Notes

This issue highlights the importance of proper asynchronous operation handling in React Native and Expo applications. Always consider the timing of asynchronous operations and handle potential initialization delays gracefully.