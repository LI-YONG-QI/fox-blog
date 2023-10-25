---
slug: rust-variables
title: Rust 變數
authors: fox
tags: [hola, docusaurus, rust]
---

# Overview

這篇主要在講述幾種 rust 的基本資料型態，以及宣告的方式

---

# 實例

## 宣告

`let` 開頭，且所有變數都預設為不可變更，若要變更需要再加上一個 `mut`

```rust
let a = 1;
let mut b = 2;
```

## 數字型別

- i32 有號整數，占 32 bits
- u64 無號整數，占 64 bits
- f64 / f32 浮點數
- isize / usize 根據電腦的架構來決定 size，32 bits / 64 bits

```rust
let a:i32 = 1;
let mut b = 2;
```

## Tuple

```rust
let tup: (i32, u8, bool) = (-1, 32, true);
let (x, y, z) = tup; //解構式
```

```rust
let tup: (i32, u8, bool) = (-1, 32, true);
let one = tup.0; //access
let two = tup.1;
```

## 推論

- 如果不指定型別，會有自動推論型別
  - 整數會自動推論為 i32
  - 浮點會自動推論為 f64

```rust
let i:i8 = 1; //顯性推論
let y = 1; //沒有指定型別的話，隱性推論 i32
let x = 1.0; //沒有指定型別的話，隱性推論 f64
```

---

# 原理

設定預設為不可變變數，推斷是因為想要盡量減少變數變化這件事情，因為在 js 當中，能宣告為 const 就盡量宣告，來減少不必要 bug 發生的可能性。

---

# 想法總結

Rust 在變數的定義上除了預設都是不可變以外，沒有什麼其餘太特別的地方，有點基礎電腦科學的人都能理解位數

---

# 來源

- https://doc.rust-lang.org/book/
