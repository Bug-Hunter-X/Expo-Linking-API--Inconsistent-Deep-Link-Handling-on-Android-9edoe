# Expo Linking API: Inconsistent Deep Link Handling on Android

This repository demonstrates an uncommon bug related to the Expo `Linking` API's inconsistent behavior, specifically on Android devices. The `Linking.addEventListener` function, used to listen for deep links, does not always reliably trigger.

## Problem

The core issue lies in the unreliability of the `Linking.addEventListener` function. In certain scenarios, particularly on Android, this listener fails to fire, leaving the application unresponsive to deep links. This leads to unexpected behavior and hinders the seamless integration of deep linking functionality.

## Solution

The solution involves utilizing a combination of techniques to enhance the reliability of deep link detection:

1. **`Linking.getInitialURL` for initial deep links**: This ensures that any initial deep links present upon app launch are processed.
2. **Persistent event listener**:  The event listener is maintained and doesn't rely on a single event triggering.
3. **`setTimeout` to handle potential delays**: This gives the deep link a chance to register, increasing robustness.

By implementing these strategies, we significantly improve the robustness of deep link handling and ensure consistent functionality across various scenarios.