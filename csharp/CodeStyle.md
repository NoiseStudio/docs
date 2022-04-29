# Code Style
Noise Studio's code style for the C# programming language.
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
> The groups must be arranged in the same order as here.<br><br>
Elements in groups must be sorted in the order of modifiers:<br>
`static > abstract > virtual > none`<br>
Additionally, in sorted groups of elements located in groups, you sort them into:<br>
`readonly > volatile > none`<br><br>
[See example](#sorted-groups-and-elements)

### Constants
```cs
public const int PascalCase = 5;
```

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
AnyAccessModifier Foo PascalCase => // line of code;
```
> The following ways of writing this element must be separated by a one-line gap from other elements.
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

### Events
```cs
[Attribute]
AnyAccessModifier event Foo PascalCase;
```

### Constructors
> This element must be separated by a single line gap from other elements.
```cs
[Attribute]
AnyAccessModifier Foo(Boo example, Boo secondExample) {
```

### Deconstructors
> This element must be separated by a single line gap from other elements.
```cs
~Foo() {
```

### Methods
> This element must be separated by a single line gap from other elements.

> Every public method and operator on a public type, even if it is inherited, must be documented
(if it is a part of a public API, e.g. test methods are not).
Parameters and result must also be documented.
```cs
/// <summary>
/// Documentation
/// </summary>
/// <param name="example">Documentation</param>
/// <param name="secondExample">Documentation</param>
/// <returns>Documentation</returns>
[Attribute]
AnyAccessModifier Type PascalCase(Boo example, Boo secondExample) {
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
AnyAccessModifier Type PascalCase<T0, T1>(Boo example, Boo secondExample) {
```

## Test methods
Test method naming should use PascalCase with underscores separating name of the tested method/member,
what is being tested and the expected result. For example:
```cs
[Fact]
public void Equals_SameInstance_ReturnsTrue() {
    object o = new object();
    bool result = o.Equals(o);
    Assert.True(result);
}
```

### Operators
> This element must be separated by a single line gap from other elements.

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

# Sample codes
### Sorted groups and elements
```cs
namespace Project.Foo {
    [Attribute]
    AnyAccessModifier TypeType PascalCase : Bar {

        // These regions are not required.
        #region Constants

        public const int PascalCase = 5;
        internal const int PascalCase = 5;
        protected const int PascalCase = 5;
        private const int PascalCase = 5;

        #endregion
        #region Fields

        public static readonly Foo PascalCase;
        internal static readonly Foo camelCase;
        protected static readonly Foo camelCase;
        private static readonly Foo camelCase;

        public static volatile Foo PascalCase;
        internal static volatile Foo camelCase;
        protected static volatile Foo camelCase;
        private static volatile Foo camelCase;

        public static Foo PascalCase;
        internal static Foo camelCase;
        protected static Foo camelCase;
        private static Foo camelCase;

        public readonly Foo PascalCase;
        internal readonly Foo camelCase;
        protected readonly Foo camelCase;
        private readonly Foo camelCase;

        public volatile Foo PascalCase;
        internal volatile Foo camelCase;
        protected volatile Foo camelCase;
        private volatile Foo camelCase;

        public Foo PascalCase;
        internal Foo camelCase;
        protected Foo camelCase;
        private Foo camelCase;

        #endregion
        #region Properties

        public static readonly Foo PascalCase { get; set; }
        internal static readonly Foo PascalCase { get; set; }
        protected static readonly Foo PascalCase { get; set; }
        private static readonly Foo PascalCase { get; set; }

        public static volatile Foo PascalCase { get; set; }
        internal static volatile Foo PascalCase { get; set; }
        protected static volatile Foo PascalCase { get; set; }
        private static volatile Foo PascalCase { get; set; }

        public static Foo PascalCase { get; set; }
        internal static Foo PascalCase { get; set; }
        protected static Foo PascalCase { get; set; }
        private static Foo PascalCase { get; set; }

        public readonly Foo PascalCase { get; set; }
        internal readonly Foo PascalCase { get; set; }
        protected readonly Foo PascalCase { get; set; }
        private readonly Foo PascalCase { get; set; }

        public volatile Foo PascalCase { get; set; }
        internal volatile Foo PascalCase { get; set; }
        protected volatile Foo PascalCase { get; set; }
        private volatile Foo PascalCase { get; set; }

        public Foo PascalCase { get; set; }
        internal Foo PascalCase { get; set; }
        protected Foo PascalCase { get; set; }
        private Foo PascalCase { get; set; }

        #endregion
        #region Events

        public static event Foo PascalCase;
        internal static event Foo PascalCase;
        protected static event Foo PascalCase;
        private static event Foo PascalCase;

        public event Foo PascalCase;
        internal event Foo PascalCase;
        protected event Foo PascalCase;
        private event Foo PascalCase;

        #endregion
        #region Constructors

        public TypeName(Boo example) : base(5) { ...
        internal TypeName(Boo example) : base(5) { ...
        protected TypeName(Boo example) : base(5) { ...
        private TypeName(Boo example) : base(5) { ...

        #endregion
        #region Deconstructor

        ~TypeName() { ...

        #endregion
        #region Methods

        /// <summary>
        /// Documentation
        /// </summary>
        /// <param name="example">Documentation</param>
        /// <param name="secondExample">Documentation</param>
        /// <returns>Documentation</returns>
        public static Type PascalCase(Boo example, Boo secondExample) { ...

        /// <summary>
        /// Documentation
        /// </summary>
        /// <param name="example">Documentation</param>
        /// <param name="secondExample">Documentation</param>
        /// <returns>Documentation</returns>
        internal static Type PascalCase(Boo example, Boo secondExample) { ...

        /// <summary>
        /// Documentation
        /// </summary>
        /// <param name="example">Documentation</param>
        /// <param name="secondExample">Documentation</param>
        /// <returns>Documentation</returns>
        protected static Type PascalCase(Boo example, Boo secondExample) { ...

        /// <summary>
        /// Documentation
        /// </summary>
        /// <param name="example">Documentation</param>
        /// <param name="secondExample">Documentation</param>
        /// <returns>Documentation</returns>
        private static Type PascalCase(Boo example, Boo secondExample) { ...

        /// <summary>
        /// Documentation
        /// </summary>
        /// <param name="example">Documentation</param>
        /// <param name="secondExample">Documentation</param>
        /// <returns>Documentation</returns>
        public Type PascalCase(Boo example, Boo secondExample) { ...

        /// <summary>
        /// Documentation
        /// </summary>
        /// <param name="example">Documentation</param>
        /// <param name="secondExample">Documentation</param>
        /// <returns>Documentation</returns>
        internal Type PascalCase(Boo example, Boo secondExample) { ...

        /// <summary>
        /// Documentation
        /// </summary>
        /// <param name="example">Documentation</param>
        /// <param name="secondExample">Documentation</param>
        /// <returns>Documentation</returns>
        protected Type PascalCase(Boo example, Boo secondExample) { ...

        /// <summary>
        /// Documentation
        /// </summary>
        /// <param name="example">Documentation</param>
        /// <param name="secondExample">Documentation</param>
        /// <returns>Documentation</returns>
        private Type PascalCase(Boo example, Boo secondExample) { ...

        #endregion
        #region Operators

        /// <summary>
        /// Documentation
        /// </summary>
        /// <param name="a">Documentation</param>
        /// <param name="b">Documentation</param>
        /// <returns>Documentation</returns>
        public static Foo operator *(Foo a, Foo b) {
            return new Foo(a.value * b.value);
        }

        /// <summary>
        /// Documentation
        /// </summary>
        /// <param name="a">Documentation</param>
        /// <param name="b">Documentation</param>
        /// <returns>Documentation</returns>
        internal static Foo operator *(Foo a, Foo b) {
            return new Foo(a.value * b.value);
        }

        /// <summary>
        /// Documentation
        /// </summary>
        /// <param name="a">Documentation</param>
        /// <param name="b">Documentation</param>
        /// <returns>Documentation</returns>
        protected static Foo operator *(Foo a, Foo b) {
            return new Foo(a.value * b.value);
        }

        /// <summary>
        /// Documentation
        /// </summary>
        /// <param name="a">Documentation</param>
        /// <param name="b">Documentation</param>
        /// <returns>Documentation</returns>
        private static Foo operator *(Foo a, Foo b) {
            return new Foo(a.value * b.value);
        }

        #endregion

    }
}
```
