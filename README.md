# OmniKernel for Android

Many platforms face challenges when converting code between Android and iOS. These challenges often lead to bugs and issues. Some companies turn to code generation tools, but this can result in losing control over the code.

OmniKernel is a new framework under development that aims to simplify this process. It makes the code between Android and iOS as similar as possible. With OmniKernel, you can almost copy and paste code from one platform to another, maintaining your native code and control.

Key Benefits:

	•	Ease of Transition: Simplifies the process of moving code between platforms.
	•	Maintains Control: Keeps your code native and in your hands.
	•	Speeds Up Development: Accelerates the development process.
	•	Standardizes Code: Ensures consistent readability and structure across platforms.

OmniKernel makes it easier for developers, allowing an Android developer to quickly understand iOS code and vice versa.

Website: https://www.schirmer.dev.br/overview/omnikernel

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
