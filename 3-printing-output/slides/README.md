# Slides 3 - Printing Output

Our Applications often are only worth as much as the user gets to see from it. While we will learn later, that some application's result is not necessarily output to the console, but maybe files that are deleted, renamed or created, the output of text to the console is still the most common and most classic response that a user can receive when running a Console Application.

- You can simply access `Console` class‘s static method `WriteLine`, passing a string parameter:

<details>
  <summary>HINT</summary>
  
You don't know what a `class`, `static`, a `method` or a `string` is, yet. We will ge tto that later.
 
</details>

### Console.WriteLine
```cs
Console.WriteLine("Hello World!");
// Output: Hello World!
```

You can simply exchange the content within the Quotation Marks, if you want different Output:

```cs
Console.WriteLine("Covfefe");
// Output: Covfefe
```

You will later also see other parameters passed into `WriteLine`, without `""`:

```cs
Console.WriteLine(5);
// Output: 5
Console.WriteLine(enemy);
// Output: UnityEngine.GameObject
``` 

### Console.Write
- If you don't want a Line-break after your Output, use `Write` instead:
```cs
Console.Write("Hello");
Console.Write("World");
Console.Write(5);
// Output: HelloWorld5
```