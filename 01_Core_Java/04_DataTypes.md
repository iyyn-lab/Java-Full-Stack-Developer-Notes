# 📦 Java Data Types: Storing Data the Right Way

We have **multiple data types** to store different kinds of data in Java.

---

## 🗂️ Two Categories of Data Types

```
Data Types
├── Primitive Data Types   (in-built)
└── Non-Primitive Data Types  (we will see later)
```

This guide focuses on **primitive data types**.

---

## 🧱 What Are Primitive Data Types?

- They are **in-built** data types.
- They are the **simple basics** for working with:
  - Numbers
  - Decimal (float) values
  - Characters
  - `true` / `false`

> 💡 Java has **8 primitive data types**, grouped into **4 categories**.

| Category | Data Types |
| :--- | :--- |
| **Integer** (whole numbers) | `byte`, `short`, `int`, `long` |
| **Float** (decimal numbers) | `float`, `double` |
| **Character** (single letters/symbols) | `char` |
| **Boolean** (`true` / `false`) | `boolean` |

---

## 🔢 1. Integer Types

Used to store **whole numbers** (positive, negative, or zero): `... -2, -1, 0, 1, 2 ...`

Java gives you **four sizes** so you can pick the smallest one that fits your needs.

| Type | Size | Bits | Range | Suffix Required? |
| :--- | :--- | :--- | :--- | :--- |
| `byte` | 1 byte | 8 bits | −2⁷ to 2⁷−1 (−128 to 127) | ❌ No |
| `short` | 2 bytes | 16 bits | −2¹⁵ to 2¹⁵−1 | ❌ No |
| `int` | 4 bytes | 32 bits | −2³¹ to 2³¹−1 | ❌ No |
| `long` | 8 bytes | 64 bits | −2⁶³ to 2⁶³−1 | ✅ Yes — add `l` or `L` |

### 📌 Key points

- **`int`** is the **default** choice for normal whole numbers.
- **`long`** is used when you need **bigger values**.
  - After the number, you **must add `l` or `L`**.
  ```java
  long l = 5854l;
  ```
- **`short`** and **`byte`** are used when you want to **save memory**.
  ```java
  byte num = 8;
  ```

> 💡 **Rule of thumb:** Use the **smallest type** that fits your data to save memory.

---

## 🌊 2. Float Types (Decimal Numbers)

Used to store **decimal values** like `1.5`, `3.2`, `5.8`.

Java has **two** float types:

| Type | Size | Precision | Default? |
| :--- | :--- | :--- | :--- |
| `float` | 4 bytes | Lower precision | ❌ |
| `double` | 8 bytes | Higher precision | ✅ Default |

### 📌 Key points

- By **default**, any decimal value in Java is treated as a **`double`**.
- **`float`** is good when:
  - You have **limited/precision-sensitive** values.
  - You want to save memory.
- **`double`** is good when:
  - You do **scientific calculations**.
  - You need **maximum precision**.

### ⚠️ The `float` trap

```java
double num = 5.6;   // ✅ fine — 5.6 is a double by default
float num = 5.6;    // ❌ ERROR — 5.6 is double by default
```

**Why?** Because Java sees `5.6` and assumes it's a `double`. Assigning a `double` to a `float` loses precision.

### ✅ Fix: add `f` after the number

```java
float num = 5.6f;   // ✅ correct — 'f' tells Java it's a float
```

> 💡 **Remember:** Decimal → `double` by default. Use `f` suffix to make it a `float`.

---

## 🔤 3. Character Type (`char`)

Used to store a **single character** — a letter, digit, or symbol.

| Language | Size of `char` |
| :--- | :--- |
| **Java** | **2 bytes (16 bits)** |
| C / older languages | 1 byte |

### 📌 Key points

- Java uses **Unicode**, **not ASCII**.
  - This gives a **much bigger range** — you can use characters from **any language**.
- A `char` holds **exactly one character**.
- Use **single quotes** (`'k'`) for `char`.
- Use **double quotes** (`"hello"`) for `String`.

```java
char c = 'k';       // ✅ single character, single quotes
// char c = "k";    // ❌ error — double quotes make a String
```

---

## ✅ 4. Boolean Type (`boolean`)

Used to store **only two values**:

- `true`
- `false`

```java
boolean b = true;
```

### 📌 Key points

- In Java, boolean works **only with `true` and `false`**.
- It does **not** work with `0` and `1` (unlike C or other languages).

```java
boolean b = 1;      // ❌ error
boolean b = true;   // ✅ correct
```

---

## ❌ Example 1: The `float` Error

Here is a program where `float f = 5.8;` causes an error.

```java
class DataTypes {
    public static void main (String a[]){

        int num1 = 9;
        byte by = 127;
        short sh = 558;
        long l = 5854l;

        float f = 5.8;   // ❌ ERROR
    }
}
```

**Output:**

```
D:\Java Course> javac DataTypes.java
DataTypes.java:9: error: incompatible types: possible lossy conversion from double to float
        float f = 5.8;
                  ^
1 error
```

### 🔍 What went wrong?

- `5.8` is a **`double`** by default.
- Assigning a `double` to a `float` risks losing precision.
- Java refuses this unless you **explicitly say** it's a float.

---

## ✅ Example 2: The Correct Version

Here is the same program with the correct data types.

```java
class DataTypes {
    public static void main (String a[]){

        int num1 = 9;
        byte by = 127;
        short sh = 558;
        long l = 5854l;

        float f = 5.8f;      // ✅ 'f' suffix
        double d = 5.8;      // ✅ double by default

        char c = 'k';        // ✅ single quotes

        boolean b = true;    // ✅ true/false only
    }
}
```

> 📝 **Note:** No output will be shown because we are **not printing anything** — we are only **declaring and assigning variables**.

---

## 🧩 Non-Primitive Data Types

Java also has **more data types** beyond primitives. These are **not** primitive types.

### The common non-primitive types

| Type | What it is |
| :--- | :--- |
| `String` | A sequence of characters (text) |
| **Arrays** | A collection of values of the **same type** |
| **Classes** | Blueprints for creating objects (user-defined) |
| **Objects** | Instances of a class |
| **Interfaces** | Contracts that classes can implement |
| **Enums** | A fixed set of named constants |

> 💡 We will cover each of these in detail later.

---

## 📌 Quick Summary

| Category | Type | Size | Notes |
| :--- | :--- | :--- | :--- |
| Integer | `byte` | 1 byte | Range: −128 to 127 |
| Integer | `short` | 2 bytes | Range: −2¹⁵ to 2¹⁵−1 |
| Integer | `int` | 4 bytes | Default for whole numbers |
| Integer | `long` | 8 bytes | Add `l` / `L` suffix |
| Float | `float` | 4 bytes | Add `f` suffix |
| Float | `double` | 8 bytes | Default for decimals |
| Character | `char` | 2 bytes | Unicode, single quotes |
| Boolean | `boolean` | JVM-dependent | Only `true` / `false` |
| Non-Primitive | `String`, Arrays, Classes, Objects, Interfaces, Enums | — | Reference types |

> 💡 **Two golden rules:**
> 1. Decimal values are **`double`** by default — add `f` for `float`.
> 2. Whole numbers are **`int`** by default — add `l` for `long`.2¹⁵