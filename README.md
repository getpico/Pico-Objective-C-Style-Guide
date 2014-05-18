Pico-Objective-C-Style-Guide
============================

These guidelines are founded on Apple's existing Coding Guidelies for Cocoa, such that if something is not explicitly stated below, it's a good idea to defer to Apple's style guide.

This style guide applies equally to both iOS and Mac development.

Lastly, this guide is strongly influenced by The New York Time's and Sam Soffe's Objective-C style guides, so thank you.


##Operators

```objective-c
NSString* foo = @"bar";
NSInteger count = 10;
count += 1;
count++;
count = 8 + 2;
```

Objects should be initialized with the pointer asterick immidiately following the class's name without a space. Shorthand operators such as `++` and `--` are declared after the variable. Operators should be surrounded by spaces if there is more than one operand. 


##Types

Apple defined types are preferred over primitives for 64-bit safety and consistancy. For example, `NSInteger` and `CGFloat` are preferred over `int` and `float`. An exception to this would be in `for` loops, where using `int` for brevity is acceptable. 


#Methods

```objective-c
- (void)exampleMethod
{
	if (success) {
		// Do stuff
	}
}

- (NSString *)exampleMethodWithParameters:(NSObject *)object image:(UIImage *)image;

```

There should be a new line for the opening and closing braces of a method implementation. However, for method calls within a method, the opening brace should be on the same line. 

There should always be one space after the `+` or `-` of a method. If the return type is an object, the format should follow `- (NSObject *)`. 


#Whitespace

```objective-c
- (void)someMethod
{
	NSInteger min = 0;
	NSInteger max = 5;
	
	if (max > min) {
		// Do stuff
	}
}


#pragma mark - IBActions

- (IBAction)someAction:(id)sender
{
	// Do other stuff
}
```

- Indent with 4 spaces, not tabs.
- There should be exactly one blank line between methods for clarity, but never any more.
- Pragma marks should be used to organize code. Pragma mark definitions should have two blank lines above it, providing a bit more visual separation.
- Whitespace within method implementations can be used to separate functionality, but use only one blank line to do so.


#Control Flow

###Conditionals 

```objective-c
if (user.isSubscriber) {
	// Hooray!
}
else {
	// Oh no.
}

```
- Conditional bodies should always use braces, no matter what. 
- `else` should open on a new line.
- There should be one space between the `if`/`for`/`switch`/etc and the opening parenthesis. Control flow keywords are not function calls, and should not be treated as such.

###Ternary Operator

No.


#Properties

```objective-c
#import <Foundation/Foundation.h>

@interface MyClass : NSObject

@property (nonatomic, retain) NSManagedObjectContext* managedObjectContext;
@property (nonatomic, assign) BOOL someBoolean;

- (void)someMethod;

@end
```

Per usual, there should only be one blank line between the parts of a header file (e.g., between the `#import` statements, the properties and the methods, etc.).

There is an order in which property attributes should be listed. `nonatomic` should always be first, followed by either `retain` or `assign`. After that should be the optional `readonly`.
