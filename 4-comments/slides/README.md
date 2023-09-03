# Slides 4 - Comments

Comments are used for documentation or for explaining complex or unclear code.

## Single-Line Comments
- The most traditional comment is a simple single-line comment, started with `//`:
```cs
// This is a single-line comment.
int x = 5;
int x1 = 3; // Everything in the same line after this symbol becomes a comment.
// Even code gets ignored: Console.WriteLine("HelloWorld!"); will not do anything.
// Comments are ignored by the Compiler and don't cost any performance
// So there is no need to be greedy with comments
```

## Multi-Line Comments
- Another useful tool for larger comments are multi-line comments.
- They are started by using `/*`
- And they end at the next occurence of a `*/`

```cs
/* This is a multi-line comment,
int y = 5;
it ends only here */
```

Problem: they can not be nested:
```cs
/* Multi-line comments don't work like braces. 
        /* One 
           ending 
       tag */ is enough to end even multiple opening tags. */

int z = 5;
```

But they can be used to comment out a small part of a line of code:
```cs
// Another use of multi-line comments:
Console.Write(/*x+y+z*/"Test");
```

## XML Documentation Comments
- If you write a library (reusable, modular code), your public `API` should be documented in `XML`.
  - Your public `API` includes public classes, interfaces and methods.
- There are exporters for `XML` documentation comments to generate `HTML` or `PDF` documentation for your code.
```cs
///<summary>
/// This is an XML documentation comment.
/// It will show up in your IDE's tooltips.
/// </summary>
/// <param name="args"> It has cool features, like giving infos on parameters. </param>
static void Main(string[] args)
{}
```

## Comments and Compilation
Comments are ignored by the compilers. So, this code here:
```cs
public void DoStuff(){
   Console.WriteLine("a");
   // Console.WriteLine("b");
   Console.WriteLine("c");
}
```

Gets compiled to this:
```cs
public void DoStuff(){
   Console.WriteLine("a");
   
   Console.WriteLine("c");
}
```

## Commenting Guidelines

- Well-written code does not require many comments.
```cs
public class Car {
   // Gets the Speed of the car. <- not a good comment!
   public int GetSpeed() {
      // needs to be multiplied with 3.61 to convert from mp/h to km/h <- good comment! Explains something that might have been cryptic else.
      return rigidbody.GetVelocity().magnitude * 3.61;
   }
}
```

- As an experienced programmer, you want to avoid spamming your code with unnecessary comments
- As an inexperienced programmer, you just want to make sure to understand next week, what you've done last week
  - So don't feel bad for putting a lot of comments in your code :)
- Learn your IDE's shortcuts for commenting / uncommenting code.
  - e.g. `Cmd` + `/` on Rider (Mac) or `Ctrl` + `K`, `Ctrl` + `C` on Windows