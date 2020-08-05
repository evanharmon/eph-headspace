# IOS DEVICE TESTING

## Summary

## Resources

## Test Local Web Server on iOS Device

1. Go to System Preferences -> Sharing -> Enable Internet Sharing -> iPhone USB
2. connect iOS device via USB
3. Enable Safari Web Inspector on iOS device
4. Open Safari on iOS device
5. Open Safari on Mac, and select the mobile web browser window. Click the menu
   Develop -> `your device name` -> `webpage address` in dropdown list
6. Change the url via the inspect console tab by entering
   `window.location = http://mylaptopname.local:3000/`
