# IOS Learning 
Share Pods among multiple target
Pod file
# Note; name needs to be all lower-case.
def shared_pods
    pod 'SSKeychain', '~> 0.1.4'
    pod 'INAppStoreWindow', :head
    pod 'AFNetworking', '1.1.0'
    pod 'Reachability', '~> 3.1.0'
    pod 'KSADNTwitterFormatter', '~> 0.1.0'
    pod 'MASShortcut', '~> 1.1'
    pod 'MagicalRecord', '2.1'
    pod 'MASPreferences', '~> 1.0'
end

target 'Sail' do
    shared_pods
end

target 'Sail-iOS' do
    shared_pods
end

PodSpec File
A Podspec file, or Spec, describes a version of a Pod library. It includes details about where the source files are located, which files to use, the build settings to apply, dependencies, frameworks used and other general metadata such as the name, version and description for the Pod.
￼


The difference in Class and Structure
Summarize the difference between Class and Structure
Comparision	Class	Structure
Type	Classes are reference types.	Structures are value types.
Inheritance	Classes have an inheritance that allows one class to inherit the characteristics of another.	Structures do not support inheritance.
Storage	Class instances are stored on the heap.	Structure properties are stored on the stack.
Initializer	We have to define the initializer manually.	Struct gets a default initializer automatically.
Thread−safe	Classes are not fully thread−safe.	The structure is thread−safe or singleton at all times.

Singleton

class LocationManager{
    static let shared = LocationManager()
     //Initializer access level change now
    private init(){}
}


Share data between multiple apps
Pasteboard
using shared keychain access.
Custom url
Password autofill
UIactivity view controller
Share kit
iCloud
Universal link



Core Data Deletion rule
* 		No Action
* 		Nullify.  If the delete rule of a relationship is set to Nullify, the destination of the relationship is nullified when the record is deleted. This is the default delete rule
* 		Cascade If a note should always have a category, the deletion of a category should automatically delete the notes associated with that category.
* 		Deny. Deny is another powerful and useful pattern. It is the opposite of the Cascade delete rule. Instead of cascading the deletion of a record, it prevents the deletion of the record. For example, if a category is associated with several notes, the category can only be deleted if it is no longer tied to any notes. This configuration prevents the scenario in which notes are no longer associated with a category.


Abstract Base class
Method  that written in the base class and its intention to be overwritten in the subclass class only and it can not be used directly is called Abstract class or Abstract Base class.  

1.Command + Shift + {      OR   Command + Shift + } For  Switch between tabs  in Xcode 
2.Command + ~    For switch between windows of Xcode or chrome
3.Sift + Command + >  OR Sift + Command + < to select whole line
4.Command + Shift + T to undo close a tab


Design Pattern
Design pattern term is mostly used to identify some object level solutions addressing common design problems following object oriented design principles. These patterns are technology/platform agnostic, pure and domain independent. So they rely on only few assumptions. Main motivation is to design more maintainable and extensible objects by loosen up object dependencies.

Architecture
Software architecture term refers to broader concept than library level object design. It is about designing and integrating databases, libraries, services, servers, configuration, communication protocols, workflows etc. Software architect should consider every non-functional requirement (reliability, scalability etc.) and choose paradigms and technologies based on them.
 
Encapsulation
Organizing properties and related operations in a class is a powerful tool for taming complexity. It even has a fancy name: encapsulation.

In Swift you can create an instance of abstract base class .Its a limitation in swift

reference semantics
variables holding a class instance actually hold a reference to that instance. If you have two variables with the same reference, changing data in one will change data in the other.

Polymorphism
polymorphism meaning “many forms”
Notice that although the instruments array’s type is [Instrument], each instrument performs accordingly depending on its class type. This is how polymorphism works in practice

Access Control
	•	private: Visible just within the class.
	•	fileprivate: Visible from anywhere in the same file.
	•	internal: Visible from anywhere in the same module or app.
	•	public: Visible anywhere outside the module.
There are additional access control related keywords:
	•	open: Not only can it be used anywhere outside the module but also can be subclassed or overridden from outside.
	•	final: Cannot be overridden or subclassed.


Value and Reference Type
In Swift everything is value type except class, functions and closure

Type inference
Swift is a type inference type language that means if you assign a value to a var or let that variable automatically refer to that data structure and can not be modified.

Reserved keywords
use escape symbol “‘”  ‘class’ to use reserved keywords of swift

Tuples



Option
? for Declaring optional type
! for implicit decraring force unwrap
 

*In a dictionary Key part should be always same datatype like Int,Float,String It can not be Any
*=== can be used to check if two instance are same
*Do While is now Repeat While
	•	if let a = value { } this is called optional binding



inout
inout with data type in function parameter let that parameter mutate in that function and its original value will change


Inline
If a function is inline, the compiler places a copy of the code of that function at each point where the function is called at compile time.

@autoclosure
An autoclosure allows you to pass an expression to a function as an argument.
By wrapping the expression in a closure, the function can decide if and when the closure is invoked. The moment the closure is invoked, the expression is evaluated.

Closures
@escaping If a closure is passed as an argument to a function and it is invoked after the function returns, the closure is escaping.

Difference between class and structure
1.Reference Type, value type
2.Classes support inheritance but structure does not
3.Since classes are reference types, they have identity. You can check if two variables refer to the same class instance using the === operator. But structure does not have identity
4.Deinitializer
5.Classes support type casting, allowing you to check and convert between different class types within an inheritance hierarchy. .Structures do not support type casting because they do not have inheritance.

Similarity
Properties
Method
Subscript
Initializers
Extendable
Adopt protocol

Class initialiser type
Designated initialiser - It should be called always either by convenience initialiser or by directly  creating instance
 Convenience initialiser - It should be called either by by creating its instance but this initialiser should have call designated initialiser from itself
convenience initializer can call another another convenience initialiser or designated initialiser in the same class  
only a designated initiator can call a superclass designated initializer


To avoid strong reference cycle
Weak - if a property can be nil at any time like optional
unowned - if it should always have a value

Class method vs static method
class methods can be overridden by subclasses. This means that a subclass can provide its own implementation of a class method that was defined in its superclass.

static methods cannot be overridden by subclasses. The method is effectively final, meaning that the implementation is fixed and cannot be changed in any subclass.

Mutating
unlike classes value type (struct and enum) can not change themselves internally To do so you need to add mutating function internally


Overflow operator
&+ overflow plus will return back to min value from max value
&- overflow minus will return back to max value from main value

For the collections 
Prefix functions can be used to get part of functions
Prefix(upTo: )
Prefix(through: )
string.characters.prefix(2)

Typealias
typealias URLRequestClosure = (String?, Int?)

Access Specifier
  open - use outside the class and subclass and override existing class and method
  Public  - use outside the module as well but can not subclass or override
  Internal (Default) - whole module
  file private - whole file
  private  - within class and its extension


Higher Order function
Foreach - iterate over an array
map - filter an array but return nil as well
flatmap -Use this method to receive a single-level collection when your transformation produces a sequence or collection for each element.
reduce operation on all element of array like add all element
compactMap -  Use this method to receive an array of nonoptional values when your transformation produces an optional value.
filter 
zip
tuple


User Label with continue


Property observers
wiliest and didset (these will only called if value change outside the class)

Use “is” to use as is kind of class and “as” for type casting

Use Final Statement to stop subclassing or overriding a method

Indirect keyword can be used when recursive enum are used

extension can not contain stored property
   
fall through continue to next statement in switch

#selector(function_name)
#keyPath(className.VariableName)


protocol protocolName : class -> to define that this protocol can only implement by a class

to iterate in reverse order 1.Stride(from:10 to:1 by:-1)    array.reversed()



Swift 4 Changes
1.Private access specifier now working in class extension as well
2.compose protocol confirmation
3.use … that define range till end index
4.String itself a collection and uses unicode scaler(emoji) in a single character
5.substring introduced to share storage of buffer string(small)
6.Double.random(in: 0..<1)
7.(0..<10).randomElement()
8.let shuffledPlaylist = playlist.sorted{ _, _ in arc4random_uniform(2) == 0 }
9.let shuffledPlaylist = playlist.shuffled()
10. Seasons.allCases.enumerated()  enumeration collection   protocol CaseIterable
11.ages.first(where: { $0.hasSuffix("teen") }),  first method
12.ages.last(where: { $0.hasSuffix("teen") }), 
13.values.allSatisfy { $0 % 2 == 0 }
14.greetings.removeAll { $0.count > 3 }
15.isOn.toggle()    toggle() method on Bool
16.




Lock is an abstract concept for threads synchronization. The main idea is to protect access to a given region of code at a time. Different kinds of locks exist:
	0.	Semaphore — allows up to N threads to access a given region of code at a time.
	0.	Mutex — ensures that only one thread is active in a given region of code at a time. You can think of it as a semaphore with a maximum count of 1.
	0.	Spinlock — causes a thread trying to acquire a lock to wait in a loop while checking if the lock is available. It is efficient if waiting is rare, but wasteful if waiting is common.
	0.	Read-write lock — provides concurrent access for read-only operations, but exclusive access for write operations. Efficient when reading is common and writing is rare.
	0.	Recursive lock — a mutex that can be acquired by the same thread many times.



Url Session

UrlSession Configuration:- 
 1.default - 
 2.ephemeral - Do not persist cookies, cache, credential
 3.background - 



1.Shuffle array
2.Extension over an array for sorting (generic for string alpha, non alpha, integer low high )
3.Sort an array of objects based on its relationship count
4.


VIPER


VIP (Clean Swift)


CustomStringConvertible
It is a protocol to allow a type to provide custom textual descriptions of themselves. Every value in Swift is convertible.
Override description property when applying CustomStringConvertible Protocol


setNeedsLayout vs layoutIfNeeded vs layoutSubviews()

https://abhimuralidharan.medium.com/ios-swift-setneedslayout-vs-layoutifneeded-vs-layoutsubviews-5a2b486da31c
setNeedsLayout()
The method setNeedsLayout for a UIView tells the system that you want it to layout and redraw that view and all of its subviews, when it is time for the update cycle. This is an asynchronous activity, because the method completes and returns immediately, but it isn’t until some later time that the layout and redraw actually happens, and you don’t know when that update cycle will be.

layoutIfNeeded()
In contrast, the method layoutIfNeeded is a synchronous call that tells the system you want a layout and redraw of a view and its subviews, and you want it done immediately without waiting for the update cycle. When the call to this method is complete, the layout has already been adjusted and drawn based on all changes that had been noted prior to the method call.

Application states




Content Hugging vs Content compression

Content Hugging Priority determines how strongly a view resists growing larger than its intrinsic content size. A higher priority means the view prefers to cling closely to its content size rather than expanding. This is useful when you want to prevent a button or label from stretching beyond the text it contains.

Compression Resistance Priority determines how strongly a view resists shrinking smaller than its intrinsic content size. A higher priority means the view pushes back against constraints that would force it to be smaller than its content.


A/B Testing
Control and Variant user group 

A/B testing is also known as split testing or bucket testing. If we come to think of it, a bucket in this case is a term used to help us differentiate between each variation. The first bucket is called the control bucket - it represents the state of the application without the new improvements or updates and can be considered a benchmark when making later comparisons. The second bucket is called the variation bucket and includes the new features or improvements to be tested. By using this concept, we can easily group and divide metrics collected during the test into their respective buckets. Let's put this into practice in a test experiment.

GCD
Grand Central Dispatch (GCD) is a low-level API for managing concurrent operations. It can help improve your app’s responsiveness by deferring computationally expensive tasks to the background. It’s an easier concurrency model to work with than locks and threads.

Understanding Queue Types
GCD provides three main types of queues:
	•			Main queue: Runs on the main thread and is a serial queue.
	•			Global queues: Concurrent queues shared by the whole system. Four such queues exist, each with different priorities: high, default, low and background. The background priority queue has the lowest priority and is throttled in any I/O activity to minimize negative system impact.
	•			Custom queues: Queues you create that can be serial or concurrent. Requests in these queues end up in one of the global queues.

The QoS classes are:
	•			User-interactive: This represents tasks that must complete immediately to provide a nice user experience. Use it for UI updates, event handling and small workloads that require low latency. The total amount of work done in this class during the execution of your app should be small. This should run on the main thread.
	•			User-initiated: The user initiates these asynchronous tasks from the UI. Use them when the user is waiting for immediate results and for tasks required to continue user interaction. They execute in the high-priority global queue.
	•			Utility: This represents long-running tasks, typically with a user-visible progress indicator. Use it for computations, I/O, networking, continuous data feeds and similar tasks. This class is designed to be energy efficient. This gets mapped into the low-priority global queue.
	•			Background: This represents tasks the user isn’t directly aware of. Use it for prefetching, maintenance and other tasks that don’t require user interaction and aren’t time-sensitive. This gets mapped into the background priority global queue.

Scheduling Synchronous vs. Asynchronous Functions
With GCD, you can dispatch a task either synchronously or asynchronously.
A synchronous function returns control to the caller after the task completes. You can schedule a unit of work synchronously by calling DispatchQueue.sync(execute:).
An asynchronous function returns immediately, ordering the task to start but not waiting for it to complete. Thus, an asynchronous function doesn’t block the current thread of execution from proceeding to the next function. You can schedule a unit of work asynchronously by calling DispatchQueue.async(execute:).

Each task you submit to a DispatchQueue is a DispatchWorkItem. You can configure the behavior of a DispatchWorkItem, such as its QoS class or whether to spawn a new detached thread.

Reasoning About Dispatch Barriers
This is the classic software development Readers-Writers Problem. GCD provides an elegant solution of creating a read/write lock using dispatch barriers. Dispatch barriers are a group of functions acting as a serial-style bottleneck when working with concurrent queues.

When you submit a DispatchWorkItem to a dispatch queue, you can set flags to indicate that it should be the only item executed on the specified queue for that particular time. This means all items submitted to the queue prior to the dispatch barrier must complete before DispatchWorkItem executes.

When DispatchWorkItem‘s turn arrives, the barrier executes it and ensures the queue doesn’t execute any other tasks during that time. Once finished, the queue returns to its default implementation.

// Write
concurrentPhotoQueue.async(flags: .barrier) { [weak self] in 
      guard let self = self else { return }
      // 2 
     self.unsafePhotos.append(photo) 
      // 3 
     DispatchQueue.main.async { [weak self] in                                                                        self?.postContentAddedNotification()
     }
       }

// Read
// 1 
 concurrentPhotoQueue.sync { 
  // 2 photosCopy = self.unsafePhotos
}

Using Dispatch Groups
With dispatch groups, you can group together multiple tasks. Then, you can either wait for them to complete or receive a notification once they finish. Tasks can be asynchronous or synchronous and can even run on different queues.

DispatchSemaphore

DispatchSemaphore in Swift is a synchronization mechanism used to control access to a shared resource by multiple threads. It helps prevent simultaneous access by limiting the number of threads that can use the resource at the same time, ensuring that only a certain number of threads can access it concurrently.

Actors
Swift actors are a new concurrency feature introduced in Swift 5.5 that provide a safe and efficient way to manage shared mutable state. Actors are a type of object that can be accessed concurrently from multiple threads, but ensure that access to their mutable state is serialized and thread-safe.

Traditionally, concurrent programming in Swift has been achieved using locks, semaphores, and other low-level synchronization primitives. While these mechanisms can be effective, they are prone to problems such as deadlocks, race conditions, and other synchronization issues that can be difficult to diagnose and debug.


@MainActor attribute ensures the logic executes on the main thread while the network request is still performed on the background queue.


Symmetric VS Asymmetric encryption algoritham
SYMMETRIC KEY?
A symmetric key is one that may be used to encrypt and decode data. This implies that in order to decrypt information, the same key that was used to encrypt it must be utilized. In practice, the keys represent a shared secret shared by two or more people that may be utilized to maintain a confidential information link.

ASYMMETRIC KEY?
Asymmetric keys are the cornerstone of Public Key Infrastructure (PKI), an encryption technique that requires two keys, one to lock or encrypt the plaintext and another to unlock or decrypt the cyphertext. Neither key performs both functions.



CommomCrypto framework
Cryptokit framework
Swift Crypto.  Swift Package Manager

What is Provisioning Profile includes
	0.	Development certificates 
  2.Uniquw Device identifiers
  3.AppID (Team ID + Bundle ID i.e. com.rtechSolution.battlestarts)
	0.	Entitlements

Certificates



Delete Rules Core Data
No Action Delete Rule
  - If the delete rule of a relationship is set to No Action, nothing happens.
Nullify Delete Rule
  - If the delete rule of a relationship is set to Nullify, the destination of the relationship is nullified when the record is deleted.This is the default delete rule.
Cascade Delete Rule
  - If a note should always have a category, the deletion of a category should automatically delete the notes associated with that category.
Deny Delete Rule
  - if a category is associated with several notes, the category can only be deleted if it is no longer tied to any notes. 

Difference between Static and Class 
static and class both associate a method with a class, rather than an instance of a class. The difference is that subclasses can override class methods; they cannot override static methods.
class properties function in the same way (subclasses can override them). 

class is used inside Reference Type(class, function):
	•	computed property
	•	method
	•	can be overridden by subclass
static is used inside Reference Type(class, function) and Value Type(struct, enum, tuple):
	•	computed property and stored property
	•	method
	•	cannot be changed by subclass

protocol MyProtocol {
//    class var protocolClassVariable : Int { get }//ERROR: Class properties are only allowed within classes
    static var protocolStaticVariable : Int { get }
    
//    class func protocolClassFunc()//ERROR: Class methods are only allowed within classes
    static func protocolStaticFunc()
}

struct ValueTypeStruct: MyProtocol {
    //MyProtocol implementation begin
    static var protocolStaticVariable: Int = 1
    
    static func protocolStaticFunc() {
        
    }
    //MyProtocol implementation end
    
//    class var classVariable = "classVariable"//ERROR: Class properties are only allowed within classes
    static var staticVariable = "staticVariable"

//    class func classFunc() {} //ERROR: Class methods are only allowed within classes
    static func staticFunc() {}
}

class ReferenceTypeClass: MyProtocol {
    //MyProtocol implementation begin
    static var protocolStaticVariable: Int = 2
    
    static func protocolStaticFunc() {
        
    }
    //MyProtocol implementation end
    
    var variable = "variable"

//    class var classStoredPropertyVariable = "classVariable"//ERROR: Class stored properties not supported in classes

    class var classComputedPropertyVariable: Int {
        get {
            return 1
        }
    }

    static var staticStoredPropertyVariable = "staticVariable"

    static var staticComputedPropertyVariable: Int {
        get {
            return 1
        }
    }

    class func classFunc() {}
    static func staticFunc() {}
}

final class FinalSubReferenceTypeClass: ReferenceTypeClass {
    override class var classComputedPropertyVariable: Int {
        get {
            return 2
        }
    }
    override class func classFunc() {}
}

//class SubFinalSubReferenceTypeClass: FinalSubReferenceTypeClass {}// ERROR: Inheritance from a final class

The difference between == and === in Swift is:
	•	The == operator checks if two values are equal. For custom types you can overload this operator to support comparisons.
	•	The === operator checks if two variables point to the same object in memory. You cannot overload this operator for custom types.

For value types, === is a meaningless operator. This is because two instances can never refer to the same object in memory.

For reference types, === is a meaningful operation because an object can be referenced by multiple variables.

To specify what happens with custom objects and == operator, you need to overload the == function outside the class/struct.

Copy-On-Write
https://medium.com/@lucianoalmeida1/understanding-swift-copy-on-write-mechanisms-52ac31d68f2f

 compactMapValues()
Swift’s compactMapValues() returns a new dictionary containing only the key-value pairs that have non-nil values as the result of transformation by the given closure so the elements of compactMapValues() are the following: 1) a dictionary, 2) the method call, 3) the transform, and 4) the closure.
let data = ["a":"1", "b":"three", "c":"///4//"]
let compactMapValues: [String: Int] = data.compactMapValues { Int($0) }
// ["a": 1] 


Certificate Pinning:-
func urlSession(_ session: URLSession, didReceive challenge: URLAuthenticationChallenge, completionHandler: @escaping (URLSession.AuthChallengeDisposition, URLCredential?) -> Void) { 

How to share data between 2 apps
1. App Groups
App Groups allow multiple apps produced by the same developer to share access to a common container. This is the most common method for sharing data between apps from the same developer.
2. UIPasteboard
UIPasteboard allows apps to share data through the system clipboard. This is a more transient way to share data.
3. Keychain Sharing
Apps can share credentials or other sensitive information using the Keychain, provided they have the same access group.
4. Custom URL Schemes
Custom URL schemes allow one app to open another and pass data via the URL.
5. Shared Keychain via iCloud Keychain
For apps needing to share credentials across devices, iCloud Keychain is an option, though it's more for device synchronization than direct inter-app communication.


Combine
Combine is a reactive programming framework introduced by Apple at WWDC 2019. It provides a declarative Swift API for processing values over time, enabling you to work with asynchronous events, handle data streams, and react to changes in your app's state. Combine is a powerful tool for handling asynchronous operations, such as network requests, timers, notifications, and user interactions, in a way that is both flexible and easy to maintain.

Key Concepts in Combine
	0.	Publisher:
	•	A Publisher is a protocol that defines a type that can emit a sequence of values over time. Publishers can emit values, complete successfully, or fail with an error.
	•	Common built-in publishers include Just, Future, PassthroughSubject, and CurrentValueSubject.
	0.	Subscriber:
	•	A Subscriber is a protocol that defines a type that can receive input from a publisher. Subscribers handle values as they arrive and can also handle completion and failure events.
	•	The most common way to subscribe to a publisher is by using the sink operator, which provides closures for handling values and completion.
	0.	Subjects:
	•	Subjects are special types of publishers that can also act as subscribers, meaning they can both emit values and receive them. They are useful for bridging imperative and reactive code.
	•	The two main types of subjects in Combine are PassthroughSubject and CurrentValueSubject.
	0.	Operators:
	•	Operators are methods that allow you to transform, filter, combine, and chain publishers to create complex data flows. Combine includes many built-in operators, such as map, filter, flatMap, merge, combineLatest, and more.
	0.	Cancellables:
	•	Combine manages subscriptions with Cancellable types. When you subscribe to a publisher, a Cancellableis returned, which you can use to cancel the subscription if needed. Typically, these are stored in a Set<AnyCancellable>.

In Combine, Subjects are special types of publishers that can also act as subscribers. This means they can both emit values and receive them. Subjects are particularly useful for bridging imperative (manual) code with reactive (declarative) code in a Combine pipeline.
There are two primary types of subjects in Combine:
	0.	PassthroughSubject
	0.	CurrentValueSubject

1. PassthroughSubject
PassthroughSubject is a type of subject that does not retain its emitted values. It simply passes through any values it receives to its subscribers. If no subscribers are listening at the time a value is emitted, that value is essentially lost.

2. CurrentValueSubject
CurrentValueSubject is a type of subject that stores the latest value it has emitted. This means that new subscribers immediately receive the current value upon subscribing, even if they subscribe after that value was set.

Summary of Differences
Feature
PassthroughSubject
CurrentValueSubject
Initial Value
Not required
Required
Value Retention
No
Yes
Subscribers' First Value
Receives values after subscription only
Receives the latest value immediately
Use Case
Broadcasting events or signals
Managing and distributing the current state

@autoclosure
The @autoclosure attribute in Swift is used to automatically wrap an expression in a closure. This can simplify function calls by allowing you to pass expressions that are implicitly converted into closures, without the need to explicitly write out the closure syntax.

func myAssert(_ condition: @autoclosure () -> Bool, _ message: String) { 
    if !condition() { print("Assertion failed: \(message)") } 
} 
 let value = 5 
myAssert(value > 10, "Value is not greater than 10")


Design Patterns:-
1.Creational
     Singleton: Ensures a class has only one instance and provides a global point of access. Used for shared resources, like a database manager.
      Factory Method: Defines a method for creating an object, but lets subclasses decide which class to instantiate. Useful for delegating object creation to subclasses.
      Prototype: Creates new objects by copying an existing object, known as a      prototype. Useful for duplicating objects without knowing their specific class.
2.Structural
    Adapter: Allows incompatible interfaces to work together by converting an object’s interface into one that a client expects.
   Decorator: Dynamically adds behaviors to an object without altering its structure, useful for extending functionality at runtime.
   Facade: Provides a simplified interface to a complex system of classes, useful for reducing complexity.
3.Behavioural
    Observer: Defines a one-to-many dependency, so when one object changes, all dependents are notified. Commonly used in event handling.
   Memento: Saves and restores an object’s internal state, useful for implementing undo functionality.

Security
Stop user capturing Login screen with credential
NotificationCenter.default.addObserver(forName: .UIApplicationUserDidTakeScreenshot, object: nil, queue: OperationQueue.main) { notification in print(“Screenshot taken!”)}

func checkScreenRecording() {
    if UIScreen.main.isCaptured {
        print("Screen is being recorded or mirrored!")
        // Show a warning or blank the sensitive part of the screen
    } else {
        print("Screen is safe")
    }
}

Observe for userDidTakeScreenshotNotification and use UIScreen.isCaptured() to restrict user to proceed further.

Prevent Screen Recording with Screen Security
override func viewWillAppear(_ animated: Bool) {
    super.viewWillAppear(animated)
    // Prevent screenshots or screen recordings
    self.view.window?.layer.contents = nil
}

KeyChain Data Protection
Risk: A keychain item added to the KeyChain with a vulnerable accessibility option may be exposed to other applications on JailBroken devices or attackers with physical access. Generally, a developer has the following actions to choose from: kSecAttrAccessibleWhenUnlocked,  kSecAttrAccessibleAfterFirstUnlock,  kSecAttrAccessibleAlways,  kSecAttrAccessibleWhenUnlockedThisDeviceOnly, kSecAttrAccessibleAfterFirstUnlockThisDeviceOnly, kSecAttrAccessibleAlwaysThisDeviceOnly.

obfuscation
Code obfuscation in iOS is a process used to make the source code of your app more difficult to understand for reverse engineers, hackers, or malicious actors. While iOS apps are generally considered secure when distributed via the App Store, obfuscation adds an extra layer of security by protecting sensitive information, business logic, or proprietary algorithms.
 
1. SwiftShield
  A tool for Swift apps that obfuscates class, method, and variable names.
  Supports symbol renaming to unreadable names.
2. LLVM Obfuscator
  A low-level obfuscation tool that works with LLVM IR.
  Requires manual integration and is very powerful for advanced obfuscation.
3.SourceMaster: Provides iOS-specific obfuscation features.
4.cocoapods-obfuscation
A plugin for CocoaPods that obfuscates Swift and Objective-C symbols.

UIKit to SwiftUI Transition
You can integrate SwiftUI views into your existing UIKit app using UIHostingController.
class ViewController: UIViewController {
    override func viewDidLoad() {
        super.viewDidLoad()

        let swiftUIView = SwiftUIView()
        let hostingController = UIHostingController(rootView: swiftUIView)

        addChild(hostingController)
        hostingController.view.frame = view.bounds
        view.addSubview(hostingController.view)
        hostingController.didMove(toParent: self)
    }
}

For highly custom views, consider using UIViewRepresentable or UIViewControllerRepresentable to embed UIKit elements in SwiftUI.

struct UIKitLabel: UIViewRepresentable {
    var text: String

    func makeUIView(context: Context) -> UILabel {
        let label = UILabel()
        label.textAlignment = .center
        return label
    }

    func updateUIView(_ uiView: UILabel, context: Context) {
        uiView.text = text
    }
}
	•	Supports symbol renaming to unreadable names.
