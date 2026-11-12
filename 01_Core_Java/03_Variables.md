# 🛠️ Why Do We Build Software?

We build software to **solve real-world problems using the virtual world**.

---

## 🌍 Real World → Virtual World

Every real-world problem now has a virtual-world solution:

| Real-World Need | Virtual Solution |
| :--- | :--- |
| Buy something from home | Amazon (online shopping) |
| Book a cab | Uber |
| Banking | Online banking |
| Almost everything | Happens online now |

> 💡 **Big idea:** We are replacing real-world solutions with virtual-world solutions.

---

## 📦 The Core: Data

When we build an application, the most important thing we work with is **data**.

An application does two main things:

1. **Takes data** from the user.
2. **Processes** that data.

And at the end, it may **store** the data in a **database**.

### The flow

```
User  ──►  Application (processing)  ──►  Database (storage)
```

- **Data comes in** from the user.
- **Processing happens** in between.
- **Data may be stored** in a database at the end.

---

## 🗄️ Database vs. Variables

During processing, we need to hold data somewhere. There are **two kinds of storage**:

### 1. Database — Permanent (Persistent) Storage

- A database is **permanent / persistent storage**.
- "Permanent" does **not** mean the data can't be changed — you **can** replace values.
- It means the data **stays there** even if you shut down your machine.
- Example: Movies or games you copy onto your laptop stay there until you delete them.

### 2. Variables — Temporary Storage

- While **processing** data, you store it in **variables**.
- Variables hold data **temporarily** — only while the program is running.

| Storage | Lifetime | Example |
| :--- | :--- | :--- |
| **Database** | Permanent (persists after shutdown) | Saved user records |
| **Variables** | Temporary (only during processing) | A number being calculated |

---

## 🔒 Java is a Strongly Typed Language

Java is called a **strongly typed language**.

This means: **every variable must have a data type**.

If you want to store data, Java requires you to declare **what kind of data** it is.

### Common data types

| Data Type | What it stores | Example |
| :--- | :--- | :--- |
| `int` | Whole numbers | `5`, `100` |
| `float` | Decimal numbers | `3.14`, `9.5` |
| `String` | Text | `"Hello"` |

> 💡 Java won't let you store data without telling it the type first.

---

## 🖨️ `print` vs. `println`

Both are used to show output, but they behave differently.

### `print` → prints on the **same line**

```java
class Hello {

    public static void main(String a[])
    {
        System.out.print(9+0);
        System.out.print(9+9);
    }

}
```

**Output:**

```
918
```

> Both numbers appear on the **same line** with no space.

### `println` → prints on a **new line**

```java
class Hello {

    public static void main(String a[])
    {
        System.out.println(9+0);
        System.out.println(9+9);
    }

}
```

**Output:**

```
9
18
```

> Each number appears on its **own line**.

### Quick comparison

| Method | Behavior | Output style |
| :--- | :--- | :--- |
| `print()` | Same line | `918` |
| `println()` | New line | `9` then `18` on next line |

---

## ; Semicolons in Java

In Java, **every statement must end with a semicolon (`;`)**.

```java
int num1 = 5;   // ✅ ends with ;
int num2 = 5;   // ✅ ends with ;
```

> ⚠️ Forget the semicolon and the code won't compile.

---

## 📝 Variable Syntax

The general syntax for creating a variable is:

```
datatype variableName;
```

### Examples

```java
int num1;        // declares an int variable named num1
int num2 = 5;    // declares and assigns a value
```

---

## 👨‍💻 Full Example: Adding Two Numbers

Here is a complete program that adds two numbers and prints the result.

```java
class Hello {

    public static void main(String a[])
    {
        int num1 = 5;
        int num2 = 5;
        int result = num1 + num2;
        System.out.println(result);
    }

}
```

**Output:**

```
10
```

### What happens step by step

1. `int num1 = 5;` → stores `5` in `num1`.
2. `int num2 = 5;` → stores `5` in `num2`.
3. `int result = num1 + num2;` → adds them and stores `10` in `result`.
4. `System.out.println(result);` → prints `10` on the screen.

---

