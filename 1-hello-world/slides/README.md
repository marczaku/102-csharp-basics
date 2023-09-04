## Slides 1 - Hello World

- Open https://dotnet.microsoft.com/download
- Download and Install .NET 7.0

<img width="418" alt="image" src="https://github.com/marczaku/102-csharp-basics/assets/7360266/6cc8b204-5c37-4cc5-a368-70ccb7ff037e">



---

## 1. Create a Project

- **The cleanest way:** Use Microsoft‘s `dotnet console` command

First on Windows:

- Open your Command Line. `Command Prompt` or short: `cmd.exe`
- You can use `cd` to check in what directory you are right now
- First, use `cd C:\Projects\` to move to the desired folder (exchange `C:` with another hard drive partition, if you like.
  - `cd` stands for change directory
  - if that directory does not exist, yet...
  - either use `mkdir C:\Projects\` to create said directory through the Command Prompt
    - `mkdir` stands for make directory
  - or create it manually through the `File Explorer`

First on Mac:

- Open your Command Line. On Mac/Linux: `Terminal`
- You can use `pwd` to check in what directory you are right now
  - `pwd` stands for print working directory
- First, use `cd ~/Projects/` to move to the desired folder
  - `cd` stands for change directory
  - if that directory does not exist, yet...
  - either use `mkdir ~/Projects/` to create said directory through the Terminal
    - `mkdir` stands for make directory
  - or create it manually through `Finder`

For Both (Windows and Mac):

- When you see that you are in the directory where you would like to create your project:
  - Then use `dotnet new console –o HelloWorld` to create a new C# console project named `HelloWorld`

<img width="570" alt="image" src="https://user-images.githubusercontent.com/7360266/134827634-56dacab3-aece-4113-aa03-f5f43188eb7e.png">

- You might want to validate its existence by opening your `File Explorer` (Windows) or `Finder` (Mac)
  - and then navigate to the folder that you have specified in the second step of these instructions

<img width="621" alt="image" src="https://user-images.githubusercontent.com/7360266/134827659-cf62aac1-578e-4791-8eba-6b01cc7853b0.png">

---

## 2. Run the Project

- Move to the newly created project folder: `cd HelloWorld`
- note that paths, that start with a `/` on Mac or `\` on Windows (or `C:\`) are called absolute paths.
  - they reference from the root directory, so if you type `/HelloWorld`, then it looks for a `HelloWorld`-Folder directly on the root of your hard drive
- paths, that do not start with a slash or backslash, are called relative paths
  - they reference from whatever working directory you are in right now
    - so if you type `HelloWorld` and you are in `C:\Projects`, it will look for `C:\Projects\HelloWorld`
    - if you type `HelloWorld` and you are in `D:\Stuff`, it will look for `D:\Stuff\HelloWorld`
  - You can use `..` to look at the parent directory
    - if you type `..\Help` and you are in `D:\Some\Folder`, it will look for `D:\Some\Help`
- Use the command `dotnet run` to run your new application
- Observe the output:

<img width="570" alt="image" src="https://user-images.githubusercontent.com/7360266/134827701-e31dc98e-e92e-4d0a-aadd-a5c12352ab26.png">

- We are done!
- The machines are truly stealing our jobs!

---

## 3. Let's have a look at all the files that were created

- `HelloWorld.csproj` – This is our C#-Project file *(short: csproj)*
- `Program.cs` – This is our only C#-Script for this Project
- `obj` – This is a temporary directory used by the compiler while building *(short for object)*
- `bin` – This is where our Binary is built to *(short for binary)*

<img src="https://user-images.githubusercontent.com/7360266/134818821-f85d79b8-bb69-43f8-92a2-b0d5fa5f1d53.png" width="400" height="300">

---

## 4. `HelloWorld.csproj`

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>
  
</Project>
```

- XML-Format
- Contains a Project using `Microsoft.Net`
- The Output-Type is an *Executable*
  - This is a program that can be executed on its own
- Target Framework is `net5.0`
  - It is the most current framework right now

---

## 5. `Program.cs`

```cs
// See https://aka.ms/new-console-template for more information
Console.WriteLine("Hello, World!");
```

Well, that's short and easy. Not long ago (2020, to be exact), it used to look like this:

```cs
using System;

namespace HelloWorld
{
  class Program
  {
    static void Main(string[] args)
    {
      Console.WriteLine("Hello World");
    }
  }
}
```

You pick for yourselves, which version you like better, but I prefer the new version, for sure! :)

---
