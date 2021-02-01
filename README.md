# SwiftyDataDetector

My attempt to use `extension`s and custom data types to make working with `NSDataDetector` more Swifty and pleasant. I have written a [blog post](https://nemecek.be/blog/78/how-to-use-nsdatadetector-to-detect-links-email-addresses-phone-numbers-and-more) about this.

For example you can construct it like this:

```swift
let detector = NSDataDetector(dataTypes: DataDetectorType.allCases)
```

And here is an example of using my `enumerateMatches` method:

```swift
detector.enumerateMatches(in: exampleText) { (range, match) in
    switch match {
    case .email(let email, let mailtoURL):
        print("Found email address: \(email)")
    case .phoneNumber(let number):
        print("Found phone number: \(number)")
    default:
        break
    }
}
```
