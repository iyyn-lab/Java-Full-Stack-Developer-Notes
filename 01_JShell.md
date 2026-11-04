# 🚀 JShell: Your Interactive Java Playground

JShell is an interactive tool built into Java (introduced in JDK 9) that lets you write and run Java code **one line at a time** and see the results immediately.

Think of it like a **calculator for Java code**—it is perfect for testing quick ideas, practicing syntax, or learning the language without having to create a full project from scratch.

---

## 🤔 What is JShell?

JShell is a **REPL** tool. REPL stands for:

- **R — Read:** It reads the line of Java code you type.
- **E — Evaluate:** It runs (executes) that code right away.
- **P — Print:** It prints the output or result on your screen immediately.
- **L — Loop:** It loops back and waits for your next line of code.

This instant feedback loop makes learning Java much faster and less frustrating for beginners.

---

## ✨ Why Use JShell?

Normally, if you want to test a single line of Java code, you have to:

1. Create a `.java` file.
2. Write a class and the `public static void main(String[] args)` method.
3. Compile the file using `javac`.
4. Run the program using `java`.

JShell skips all of those steps!

Here is why developers love it:

- **Quick Experiments:** Test a single math formula or string method in seconds.
- **No Boilerplate Code:** You don't need to write `class` or `main()` methods just to test a small idea.
- **Learn by Doing:** Change a variable or call a method and see what happens right away.
- **Explore New APIs:** Quickly test unfamiliar built-in Java tools (like `LocalDate` or `Streams`) to see how they behave.

---

## 🚦 Getting Started

### 📋 Prerequisites

Make sure you have **JDK 9 or higher** installed on your computer.

### 🏁 How to Start JShell

1. Open your **Terminal** (Mac/Linux) or **Command Prompt / PowerShell** (Windows).
2. Type `jshell` and press **Enter**.

```shell
% jshell
|  Welcome to JShell -- Version 17.0.1
|  For an introduction type: /help intro

jshell>
```

When you see the `jshell>` prompt, JShell is ready for you to type Java code!

### 🛑 How to Stop JShell

To close JShell and return to your normal terminal, type `/exit` and press **Enter**:

```shell
jshell> /exit
|  Goodbye
```

---

## ✍️ How to Use JShell: Basic Examples

JShell accepts small pieces of Java code called **snippets** (variables, math expressions, statements, methods, or classes).

> 💡 **Good to know:** You don't even need to type a semicolon (`;`) at the end of single-line statements—JShell adds it for you automatically!

### 1. Simple Math & Expressions

Type any calculation and press **Enter**. JShell calculates the answer and automatically saves it in a temporary **"scratch variable"** (like `$1`) so you can reuse it later.

```java
jshell> 2 + 2
$1 ==> 4
```

### 2. Declaring Variables

You can create variables just like you do in regular Java programs:

```java
jshell> int x = 45
x ==> 45
|  created variable x : int
```

### 3. Using Scratch Variables

You can use the temporary `$1` variable created in Step 1 inside new calculations or print statements:

```java
jshell> System.out.println($1 * 2)
8
```

### 4. Defining Methods

You can write full multi-line methods directly in JShell. While you are typing inside `{ }`, JShell shows `...>` to let you know it is waiting for you to finish the block:

```java
jshell> String twice(String s) {
   ...>     return s + s;
   ...> }
|  created method twice(String)

jshell> twice("Ocean")
$5 ==> "OceanOcean"
```

### 5. Updating (Redefining) Variables or Methods

If you want to change how a method or variable works, just type a new version of it! JShell will automatically update it on the spot:

```java
jshell> String twice(String s) {
   ...>     return "Twice: " + s;
   ...> }
|  modified method twice(String)

jshell> twice("thing")
$7 ==> "Twice: thing"
```

---

## 🛠️ Essential JShell Commands

JShell has its own built-in helper commands. Every JShell command starts with a forward slash (`/`) so JShell knows it is a command and not Java code.

| Command | Description |
| :--- | :--- |
| `/help` | Shows a list of all available JShell commands. |
| `/vars` | Lists all the variables you have created in your current session. |
| `/methods` | Lists all the methods you have defined so far. |
| `/list` | Shows all the lines of code (snippets) you have typed in this session. |
| `/reset` | Erases everything you have typed and starts a clean, fresh session. |
| `/exit` | Closes the JShell tool. |

---



### Remember: It's a Playground, Not an IDE

JShell is meant for quick testing and learning. Once your code works the way you want, copy it into a proper IDE (like **IntelliJ IDEA**, **Eclipse**, or **VS Code**) to build your real projects.