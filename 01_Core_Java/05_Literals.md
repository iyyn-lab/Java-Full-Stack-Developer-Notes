# 🔤 Java Literals: Writing Values Directly in Code

A **literal** is a **direct value** written in your code.

```java
int num1 = 9;   // 9 is a literal
```

- You can use **any value** as long as it fits within the **range** of that data type.
- If the value is inside the range → ✅ it works.
- If the value is outside the range → ❌ compile error.

Java supports many kinds of literals: **integer, binary, hexadecimal, floating-point, boolean, character, and string**.

> 📌 **How to read the examples below:** Each example is a complete program in a class called `Demo`. Save the code as `Demo.java`, then **compile** and **run** it.

---

## 🔢 1. Decimal (Base 10) Integer Literals

The normal way — just write the number.

```java
class Demo {
    public static void main(String a[]) {
        int num1 = 9;
        System.out.println(num1);
    }
}
```

**Compile & Run:**

```shell
javac Demo.java
java Demo
```

**Output:**

```
9
```

> 💡 This is **base 10** — the everyday number system.

---

## 🧮 2. Binary Literals (Base 2)

Want to write a number in **binary**? Prefix it with `0b` or `0B`.

```java
class Demo {
    public static void main(String a[]) {
        int num1 = 0b101;
        System.out.println(num1);
    }
}
```

**Compile & Run:**

```shell
javac Demo.java
java Demo
```

**Output:**

```
5
```

> 💡 `0b101` in binary = `5` in decimal.

---

## 🧪 3. Hexadecimal Literals (Base 16)

Prefix the number with `0x` or `0X`.

```java
class Demo {
    public static void main(String a[]) {
        int num1 = 0x7E;
        System.out.println(num1);
    }
}
```

**Compile & Run:**

```shell
javac Demo.java
java Demo
```

**Output:**

```
126
```

> 💡 `0x7E` in hex = `126` in decimal.

### Quick reference

| Format | Prefix | Example | Decimal value |
| :--- | :--- | :--- | :--- |
| Decimal | *(none)* | `101` | 101 |
| Binary | `0b` | `0b101` | 5 |
| Hexadecimal | `0x` | `0x7E` | 126 |

---

## ➖ 4. Using Underscores for Readability

You can put **underscores (`_`)** between digits to make **big numbers easier to read and count**.

```java
class Demo {
    public static void main(String a[]) {
        int num1 = 10_00_00_000;
        System.out.println(num1);
    }
}
```

**Compile & Run:**

```shell
javac Demo.java
java Demo
```

**Output:**

```
100000000
```

> 💡 Java **ignores the underscores** — they are only for **human readability**. The output is a normal number.
>
> You can group digits any way you like: `1_000_000`, `10_00_00_000`, etc.

---

## 🌊 5. Double Data Type — Automatic Conversion

If you assign an **integer value** to a `double`, Java **automatically converts** it.

```java
class Demo {
    public static void main(String a[]) {
        double num1 = 56;
        System.out.println(num1);
    }
}
```

**Compile & Run:**

```shell
javac Demo.java
java Demo
```

**Output:**

```
56.0
```

> 💡 The integer `56` is **widened** into `56.0` automatically — no error, no cast needed.

---

## 🔬 6. Very Big Numbers with Scientific Notation

You can write **scientific notation** using `e` (or `E`) for powers of 10.

```java
class Demo {
    public static void main(String a[]) {
        double num1 = 12e10;
        System.out.println(num1);
    }
}
```

**Compile & Run:**

```shell
javac Demo.java
java Demo
```

**Output:**

```
1.2E11
```

> 💡 `12e10` means **12 × 10¹⁰** = **1.2 × 10¹¹**, printed as `1.2E11`.

### How scientific notation works

| Literal | Meaning | Output |
| :--- | :--- | :--- |
| `12e10` | 12 × 10¹⁰ | `1.2E11` |
| `5e3` | 5 × 10³ | `5000.0` |
| `2.5e-3` | 2.5 × 10⁻³ | `0.0025` |

---

## ✅ 7. Boolean Literals

A `boolean` can only be **`true`** or **`false`** — **not** `0` or `1`.

### ❌ Wrong version

```java
class Demo {
    public static void main(String a[]) {
        boolean b = 1;
        System.out.println(b);
    }
}
```

**Compile:**

```shell
javac Demo.java
```

**Output:**

```
error: incompatible types: int cannot be converted to boolean
```

### ✅ Correct version

```java
class Demo {
    public static void main(String a[]) {
        boolean b = true;
        System.out.println(b);
    }
}
```

**Compile & Run:**

```shell
javac Demo.java
java Demo
```

**Output:**

```
true
```

> ⚠️ In Java, `boolean` does **not** accept `0` or `1` (unlike C/C++). It only accepts `true` and `false`.

---

## 🔤 8. Character Literals

A `char` stores a **single character**, written in **single quotes**.

```java
class Demo {
    public static void main(String a[]) {
        char c = 'a';
        System.out.println(c);
    }
}
```

**Compile & Run:**

```shell
javac Demo.java
java Demo
```

**Output:**

```
a
```

---

## 🔁 9. Characters Can Behave Like Integers

In Java, a `char` has a **numeric (Unicode) value** behind the scenes. So you can do arithmetic on it — but you must **cast the result back to `char`**.

```java
class Demo {
    public static void main(String a[]) {
        char c = 'a';
        c = (char)(c + 1);   // ✅ cast needed
        System.out.println(c);
    }
}
```

**Compile & Run:**

```shell
javac Demo.java
java Demo
```

**Output:**

```
b
```

### ⚠️ Why the cast?

```java
char c = 'a';
c = c + 1;   // ❌ ERROR — c + 1 becomes an int
```

**Compile:**

```shell
javac Demo.java
```

**Output:**

```
error: incompatible types: possible lossy conversion from int to char
```

Adding an `int` to a `char` produces an **`int`**, and Java won't automatically put it back into a `char` (that would be a lossy conversion). You must **cast explicitly**: `(char)(c + 1)`.

> 💡 `'a'` has Unicode value `97`. Adding `1` gives `98`, which is `'b'`. That's why the output is `b`.

---

## 📝 10. String Literals

A **String** is text, written in **double quotes**.

```java
class Demo {
    public static void main(String a[]) {
        String s = "Hello World";
        System.out.println(s);
    }
}
```

**Compile & Run:**

```shell
javac Demo.java
java Demo
```

**Output:**

```
Hello World
```

> 💡 **Single quotes** → `char` (one character).
> **Double quotes** → `String` (any number of characters).

```java
char c   = 'H';            // ✅ char — single quotes
String s = "Hello World";  // ✅ String — double quotes
```

---

## 🧠 Big Idea: They're All Literals

Everything you saw above — **numbers, binary, hex, decimals, booleans, characters, and strings** — is a **literal**.

A literal is simply a **fixed value written directly in the code**.

| Kind of Literal | Example |
| :--- | :--- |
| Integer (decimal) | `9` |
| Integer (binary) | `0b101` |
| Integer (hex) | `0x7E` |
| Integer (with underscores) | `10_00_00_000` |
| Floating-point | `56`, `5.8f`, `12e10` |
| Boolean | `true`, `false` |
| Character | `'a'` |
| String | `"Hello World"` |

> 💡 **"String literal"** specifically refers to text inside double quotes — like `"Hello World"`.

---

## 🛠️ Standard Compile & Run Pattern

Every example above uses the same two commands:

| Step | Command | Purpose |
| :--- | :--- | :--- |
| **Compile** | `javac Demo.java` | Converts `Demo.java` → `Demo.class` (bytecode) |
| **Run** | `java Demo` | JVM executes `Demo.class` and prints the output |

> 💡 **Remember:** `javac` takes the **file name** (with `.java`), while `java` takes the **class name** (no extension).