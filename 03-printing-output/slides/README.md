# Slides 3 - Printing Output

- You can simply access `Console` class‘s static method `WriteLine`, passing a string parameter:

(You don't know what a `class`, `static`, a `method` or a `string` is, yet. We will get to that later.)

## Console.WriteLine
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

## Console.Write
- If you don't want a Line-break after your Output, use `Write` instead:
```cs
Console.Write("Hello");
Console.Write("World");
Console.Write(5);
// Output: HelloWorld5
```