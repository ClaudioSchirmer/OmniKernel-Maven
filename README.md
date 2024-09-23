# OmniKernel for Android

Many platforms face challenges when converting code between Android and iOS. These challenges often lead to bugs and issues. Some companies turn to code generation tools, but this can result in losing control over the code.

OmniKernel is a new framework under development that aims to simplify this process. It makes certain pieces of code between Android and iOS as similar as possible. With OmniKernel, you can almost copy and paste these code snippets from one platform to another, while still maintaining your native code and control.

Key Benefits:

	•	Ease of Transition: Simplifies the process of moving code between platforms.
	•	Maintains Control: Keeps your code native and in your hands.
	•	Speeds Up Development: Accelerates the development process.
	•	Standardizes Code: Ensures consistent readability and structure across platforms.

OmniKernel makes it easier for developers, allowing an Android developer to quickly understand iOS code and vice versa.

Documentation: https://www.schirmer.dev.br/overview/omnikernel

Maven URL: https://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:x-oauth-basic@maven.pkg.github.com/ClaudioSchirmer/OmniKernel-Maven 
> Due to restrictions, this token is provided with read-only access to allow downloading the package

# Example
## HttpClient for Android:
```kotlin
suspend fun testExample() {
    val omniClient = OmniClient(scheme = OmniClientScheme.Http, host = "host.com")
    val omniResponse = omniClient.postJson(path = "/path", body = YourClass(value = "value"))
    if (omniResponse.successfullyReceived()) {
        val yourClass: YourClass = omniResponse.decode()
        // Use yourClass
    }
}
```
## HttpClient for iOS: 
```swift
func testExample() async throws {
    var omniClient = OmniClient(scheme: OmniClientScheme.Http, host: "host.com")
    let omniResponse = try await omniClient.postJson(path: "/path", body: YourClass(value: "value"))
    if (omniResponse.successfullyReceived()) {
        let yourClass: YourClass = try omniResponse.decode()
        // Use yourClass
    }
}
```
iOS: https://github.com/ClaudioSchirmer/OmmiKernel-XCFramework
