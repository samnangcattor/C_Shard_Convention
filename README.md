# C Sharp Convention
C# - Naming Standards

# Why Coding Standards

Simple: maintainability. If, 6 months down the line, your customer isn't too happy with the product and wants an enhancement in the application you have created, you should be able to do it without introducing new bugs. There are a lot of other good reasons, but this is the one which concerns us more than anything else.
Not following any standard is like going with a temporary solution (which might lead to a permanent problem) and, as you will see, it takes less effort to keep in mind a few simple measures than to do haphazard coding.
All you have to do is study good standards once and keep them in the back of your head. Trust me; it's worth it.

# Contents

1. Naming - What is meant by meaningful names
2. Casing - When to use PascalCase and when camelCase
3. Generics - Proper usage
4. Delegates - Proper usage
5. Miscellaneous - Some short tidbits
6. Common Pitfalls - Mistakes we should watch out for
7. References - Where to get more information

# Naming

"The beginning of wisdom is to call things by their right names" - Chinese Proverb
"Meaningful" is the keyword in naming. By meaningful names, I mean concise names that accurately describe the variable, method or object. Let's see how this would be in C#:
Namespaces - Names should be meaningful and complete. Indicate your company or name, product and then your utility. Do not abbreviate.

   Classes - Class names should always be a noun and, again, should be meaningful. Avoid verbs
``` csharp
// Good
namespace CompanyName.ProductName.Utility

// Bad
namespace CN.PROD.UTIL
 
// Good
class Image
{
   ...
}

class Filters
{
   ...
}
 
// Bad
class Act
{
   ...
}

class Enhance
{
   ...
}
```
   Methods - Always use a verb-noun pair, unless the method operates on its containing class, in which case, use just a verb.
```  csharp
// Good
public void InitializePath();
public void GetPath();
public void ShowChanges();
public void System.Windows.Forms.Form.Show();
 
// Bad
public void Path();
public void Changes();
``` 
   Methods with return values - The name should reflect the return value.
```  csharp
// Good
public int GetImageWidth(Bitmap image);
 
// Bad
public int GetDimensions(Bitmap image);
```
   Variables - Do not abbreviate variable names. Variable names should again be descriptive and meaningful.
```  csharp
// Good
int customerCount = 0;
int index = 0;
string temp = "";
 
// Bad
int cc = 0;
int i = 0;
string t = "";
```
   Private member variables - Prefix class member variables with m_.
```  csharp
public class Image
{
   private int m_initialWidth;
   private string m_filename;
   ...
}
```
   Interfaces - Prefix all interface names with I. Use a name that reflects an interface's capabilities, either a general noun or an "-able".
```  csharp
interface IClock
{
   DateTime Time { get; set; }
   ...
}
 
interface IAlarmClock : IClock
{
   void Ring();
   DateTime AlarmTime { get; set; }
   ...
}
 
interface IDisposable
{
   void Dispose();
}
 
interface IEnumerable
{
   IEnumerator GetEnumerator();
}
```
   Custom attributes - Suffix all attribute class names with Attribute. The C# compiler recognizes this and allows you to omit it when using it.
```  csharp
public class IsTestedAttribute : Attribute
{
   public override string ToString()
   {
      return "Is Tested";
   }
}
 
//"Attribute" suffix can be omitted

[IsTested]
public void Ring();
```
   Custom exceptions - Suffix all custom exception names with Exception.
```  csharp
public class UserNotExistentException :
    System.ApplicationException
{
   ...
}
```
   Delegates - Suffix all event handlers with Handler; suffix everything else with Delegate.
```  csharp
public delegate void ImageChangedHandler();
public delegate string StringMethodDelegate();
```

# Casing

   C# standards dictate that you use a certain pattern of Pascal Casing (first word capitalized) and Camel Casing (all but first word capitalized).
   Pascal Casing - use PascalCasing for classes, types, methods and constants.
```  csharp
public class ImageClass
{
   const int MaxImageWidth = 100;
   public void ResizeImage();
}
 
enum Days
{
   Sunday,
   Monday,
   Tuesday,
   ...
}
```
   Camel Casing - use camelCasing for local variables and method arguments.
``` csharp
int ResizeImage(int imageCount)
{
   for(int index = 0; index < imageCount; index++)
   {
      ...
   }
}
```

# Delegates
   Use delegate inference instead of explicit delegate instantiation.
``` csharp
public delegate void ImageChangedDelegate();
public void ChangeImage()
{
   ...
}
 
// Good
ImageChangedDelegate imageChanged = ChangeImage;
 
// Bad
ImageChangedDelegate imageChanged =
   new ImageChangedDelegate(ChangeImage);
```
   Use empty parenthesis on anonymous methods without parameters.
``` csharp
public delegate void ImageChangeDelegate();
ImageChangedDelegate imageChanged = delegate()
{
   ...
}
```
