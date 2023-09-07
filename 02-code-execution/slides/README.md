# Slides 2 -  Script Execution

- C# Code is executed from top to bottom.
- Every statement in C# needs to be separated by a Semicolon `;`
- Empty statements are okay.

```cs
Console.WriteLine("First.");
Console.WriteLine("Second.");
;
```

Output:
```
First.
Second.
```

The language cares about White-spaces, tabs and newlines only as a method of separate words.
- e.g. `namespace` is a keyword and `Foo` an identifier. Those two words should be separate:

```cs
name space Foo { // WRONG
}

namespaceFoo { // WRONG
}

namespace Foo { // CORRECT
}
```

But otherwise, it does not really care about your formatting
``` cs
namespace Foo{} // OKAY

namespace    
Foo {} // OKAY

namespace Foo
{
} // OKAY

Console.WriteLine("Hi"); // OKAY
Console.WriteLine(
  "Hi"
)
; // OKAY
             Console.WriteLine(":|"); // OKAY
```

## Guidelines
There is some general guidelines, though that are well established.
- We will learn them step by step.
- IDEs can be and are configured to bring it to your attention when your formatting is off.

```cs
Console.WriteLine("A");
  Console.WriteLine("B");
Console.WriteLine("C");
```

## Reformat

If your formatting is broken
- can use the `Reformat Code` Command to fix it.
- make sure to bind it to a command.

