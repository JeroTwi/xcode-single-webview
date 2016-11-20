# Single Webview project for xcode in swift
An xcode project that with single webview(UIWebView) that opens external URL, for hybrid web app debug or test use.

- Swift
- Constrains ready. Fullscreen view with hidden status bar.
- The default URL has been set to "http://www.youtube.com".
- In Info.plist, the `Allow Arbitrary Loads` Key has been set to `YES`, so that it supports `http://` links. If you want to support secure `https://` links only, please set it to `NO`.

#### Customize the URL
Please go to ViewController.swift and change the URL string to your expected URL.

```swift
        let url = NSURL(string: "http://www.youtube.com") // Customize your URL here
```

#### Turn On Status Bar
By default, the Status Bar is turned off. you will see the web in fullscreen view. If you want to show the status bar on the webciew. Please go to ViewController.swift, and change the `return true` to `return false` on follow section. As the status bar will overlap your webview, you might want to change the `constant` value for the `Trailing Space To: Superview` in xcode to prevent it effects the webview visual style in some cases.

```swift
        override func prefersStatusBarHidden() -> Bool {
                return true // Change 'true' to 'false' here
        }
```

#### Other customizations
Caching for the URL is disabled and the 'mediaPlaybackRequiresUserAction' is set to false to enable HTML autoplay (comes in handy on IOS 9.3 and lower).
