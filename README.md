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

``` csharp
//Good
namespace CompanyName.ProductName.Utility
//Bad
namespace CN.PROD.UTIL
   Classes - Class names should always be a noun and, again, should be meaningful. Avoid verbs
 
//Good
class Image
{
   ...
}
class Filters
{
   ...
}
 
//Bad
class Act
{
   ...
}
class Enhance
{
   ...
}
```
