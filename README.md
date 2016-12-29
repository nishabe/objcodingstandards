# Objective-C Coding Standards
## 1. Best Practices
1. Avoid using Primitive datatypes.  
2. Always use 'YES' or 'NO' for BOOL and not string literals. 'Use YES/NO' rather than 'true/false'. 
3. Avoid multiple return statements.  
4. Never modify loop's index while it is running as it will hard for reviewer to review and most importantly it is not good
practice.  
5. try catch finally:   
  Never do any work on catch block other than error handling. Always have finally block.  
6. Avoid 'performselector' and use completion blocks.
7. User-facing strings should be in a resource file, not hard-coded in a view controller.  
8. Don't handle view related actions in class which are not based on view controller, go for delegates or notifications for
posting instead.  
9. enums :  
  Use enumeration wherever possible and always ensure the enum name is followed as per Apple's standard.  
  Use enumerations for groups of related constants that have integer values.  
10. Unimplemented code blocks, which are added by Xcode can be removed, especially when you are not overriding them.  
  e.g: didReceiveMemoryWarning
11. Notification : 
  Limit using Notifications. If the same can be handled using delegates,use delegates.  
  Notifications should be declared in header files of the classes that publish the notification as extern NSString * const notificationName.
  e.g: ABC<className><NotificationName>Notification , where ABC is the prefix denoting the company.    
12. Registering for a notification should follow by unregistering for the same.  
13. Don’t include any constant strings or magic Numbers. Always declare a constant at the top of file and use.   
  e.g:  NSString * const kInvalidData = @"";   
14. Variable Scope:   
  If a value is used several times in a method, it should be promoted to a variable or constant within the method.   
  If a value is used several different places in a code file, it should be promoted to a class-level constant in the implementation file.  
  If a value is used in several different code files it should be promoted to a constants file.  
15. iVars (instance variables): Choose between ivars and properties wisely. 
  ivars can be used in some cases like if we don’t want to change the value from some other classes. 
  Never use '_' as a prefix for ivar since it is reserved for Apple's use.   
16. Reusability : Always check for reusable code. 
  If the same lines of code are written at multiple places, then include those lines under a function and use so that number of
  lines can be reduced.  
17. Methods that just call super class methods don't need to exist  
18. Properties with types that have mutable subtypes (NSArray, NSString, NSDictionary, etc) should always be declared as
    copy. This prevents unwanted object mutation.  
19. Always update the UI from the UI thread  

## 2. Naming Standards

1. Use camelCasing for naming Functions  
2. Never abbreviate variable names, function names etc.   
  If you are forced to follow the existing abbreviation, check the possibility of taking ownership for revising it.
3. Method name should self-explain the purpose. Variable names should have self describing , readable and meaningful names.  
4. For methods that represent actions an object takes, start the name with a verb.  
5. Method name should state what will happen and not pre or post conditions/expectations.  
6. Objects decorated with __weak should have that as part of their name-- weakRequest, weakSelf, etc.  
7. Use modal verbs (verbs preceded by 'can', 'should', 'will', and so on) to clarify meaning, but don't use 'do' or 'does'.
8. Don't use the underscore character as a prefix for your private methods. Apple reserves this convention.
9. Use class names in enum declarations. This will prevent naming collisions in the future.
10. Use k<class name><constant name> to name constants and defines  
11. Constants:   
  Use enumerations for groups of related constants that have integer values. Use const to create constants for floating point values. 
  You can use const to create an integer constant if the constant is unrelated to other constants; otherwise, use enumeration.
  In general, don’t use the #define preprocessor command to create constants.  
  For integer constants, use enumerations, and for floating point constants use the const qualifier.
  
## 3. Code Asthetics   
  
1. Line spacing should divide code into meaningful blocks.  
2. Ensure adequate space is left and make sure that line spacing count is not more than one line, at any case.  
3. Ensure enough space between control statements, make sure it is more readable.   
4. Avoid adding blank spaces and new lines between codes. Avoid unwanted tab spaces.   
5. Limit, line's character length within 100 characters.  
6. No function should be more than 40 lines. Make sub-functions. 
  Complete function should be visible in single screen without scrolling.  
7. Avoid commented lines being pushed.  
8. Include proper comments. Code should be commented and formatted properly.  
9. Use Control + I for auto formatting. Intent multi-line statements properly
10. We shall have the FIXME , TODO comments of X-Code to hint the places where there are workarounds for API issue.
  That will be very evident when the review is done and the reviewer can skip the code block when they review.   
  // FIXME: Work around for API Issue   
  // TODO: Remove the workaround starts here ...    
  // TODO: Work around Code ends here  
11. Use Pragma-- marks for each function for better structuring and reordering  

## 4. Source Version Control

1. Before commit, do spell check for the new or modified function names, and other strings. Especially the user facing ones. 
  No spelling mistakes should be there anywhere in the code. In comments, variable names and anywhere else.   
2. Be clear and elaborate on commit messages.   
3. Fix all Warnings and Static Analyzer leaks before commit   
4. Make sure the new changes does not impact the memory utilization of the application   
5. Ensure that NSLogs are removed before pushing the code. Use DDLog only if it is necessary.   
6. Run the existing unit test cases to make sure nothing has broken.  
  Do one round of regression testing to make sure all the features are working properly.  
7. Keep the standard while naming the GIT branches. It should be either all small or pascal case, but not the mix of all three. 
  Rememeber, GIT is case sensitive.

#### Reference
Suggested Link   
https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/CodingGuidelines/CodingGuidelines.html     
https://en.wikipedia.org/wiki/Code_smell    
https://en.wikipedia.org/wiki/Don%27t_repeat_yourself    
http://blog.codinghorror.com/the-broken-window-theory/

