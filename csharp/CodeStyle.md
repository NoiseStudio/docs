# Code Style
Used by the Noise Studio code style for the C# programming language.
#

> Every element that supports an access modifier must have it defined. Include `private`.

## Comments
Single line comment:
```cs
// Comment
```
Multiline comment:
```cs
/*
Comment
*/
```

## Code blocks
```cs
{
    // code
}
```

## Regions
```cs
{
    #region Example
    if(true) {
        // code
    }
    #endregion
}
```

## Preprocessor directives
```cs
{
    #if (DEBUG && !EXAMPLE)
        // code
    #elif (!DEBUG && EXAMPLE)
        // code  
    #else
        // code
    #endif
}
```

## Type definitions
> Each type must be in a separate file and types cannot be nested.
```cs
namespace Project.Foo {
    [Attribute]
    AnyAccessModifier TypeType PascalCase : Bar {
    } 
}
```
or for interfaces:
```cs
namespace Project.Foo {
    [Attribute]
    AnyAccessModifier interface IPascalCase : Bar {
    } 
}
```
Generic:
```cs
namespace Project.Foo {
    [Attribute]
    AnyAccessModifier TypeType PascalCase<T0, T1> {
    } 
}
```

## In Type definitions
> Elements in groups must be sorted in the order of modifiers:<br>
static > abstract > virtual > none
### Fields
Public:
```cs
[Attribute]
public Foo PascalCase;
```
Internal:
```cs
[Attribute]
internal Foo camelCase;
```
Protected:
```cs
[Attribute]
protected Foo camelCase;
```
Private:
```cs
[Attribute]
private Foo camelCase;
```

### Properties
```cs
[Attribute]
AnyAccessModifier Foo PascalCase { get; set; }
```
```cs
[Attribute]
AnyAccessModifier Foo PascalCase { 
    get {
        // code
    }
    set {
        // code
    }
}
```
```cs
[Attribute]
AnyAccessModifier Foo PascalCase { 
    get => // line of code;
    set => // line of code;
}
```
```cs
[Attribute]
AnyAccessModifier Foo PascalCase => // line of code;
```

### Events
```cs
[Attribute]
AnyAccessModifier event Foo PascalCase;
```

### Constructors
```cs
[Attribute]
AnyAccessModifier Foo(Boo example, Boo secondExample) {
```

### Methods
> Every public method and operator on a public type, even if it is inherited, must be documented. Parameters and result must also be documented.
```cs
/// <summary>
/// Documentation
/// </summary>
/// <param name="example">Documentation</param>
/// <param name="secondExample">Documentation</param>
/// <returns>Documentation</returns>
[Attribute]
AnyAccessModifier Type Foo(Boo example, Boo secondExample) {
```
Generic:
```cs
/// <summary>
/// Documentation
/// </summary>
/// <param name="example">Documentation</param>
/// <param name="secondExample">Documentation</param>
/// <returns>Documentation</returns>
[Attribute]
AnyAccessModifier Type Foo<T0, T1>(Boo example, Boo secondExample) {
```

### Operators
> Every public method and operator on a public type, even if it is inherited, must be documented. Parameters and result must also be documented.
```cs
/// <summary>
/// Documentation
/// </summary>
/// <param name="a">Documentation</param>
/// <param name="b">Documentation</param>
/// <returns>Documentation</returns>
[Attribute]
AnyAccessModifier static Foo operator *(Foo a, Foo b) {
    return new Foo(a.value * b.value);
}
```
```cs
/// <summary>
/// Documentation
/// </summary>
/// <param name="a">Documentation</param>
/// <param name="b">Documentation</param>
/// <returns>Documentation</returns>
[Attribute]
AnyAccessModifier static Foo operator /(Foo a, Foo b) {
    if(b.value == 0)
        throw new DivideByZeroException();
    return new Foo(a.value / b.value);
}
```

## Variables
> Do not use `var`.
```cs
Foo camelCase = new Foo();
```
Generic:
```cs
Foo<T> camelCase = new Foo<T>();
```

## Instructions
> Code blocks for instructions are not required.

if:
```cs
if (true)
    // line of code
```
```cs
if (true) {
    // code
} else if (false) {
    // code
} else {
    // code
}
```
switch:
```cs
switch (a) {
    default:
        // code
        break;
    case Foo.A:
        // code
        break;
}
```
while:
```cs
while (true) {
```
do while:
```cs
do {
    // code
} while (true);
```
for:
```cs
for (int i = 0; i < a.Length; i++) {
```
foreach:
```cs
foreach (int a in b) {
```

## Invoking
Creating new object:
```cs
new Foo();
```