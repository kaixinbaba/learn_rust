# Hello Rust
本仓库旨在入门Rust基础语法（基于[Rust中文教程](https://kaisery.github.io/trpl-zh-cn/))，并且横向比较同类型语法在Java和Python中的实现

## 基础
### hello world
```rust
fn main() {
    println!("hello world");
}
```
```java
public static void main(String[] args) {
    System.out.println("hello world");
}
```
```python
print('hello world')
```
### 注释
```rust
// 单行注释

///文档注释
///支持markdown
///

//!另一种文档注释
//!
//!
```
```java
// 单行注释

/*
 * 多行注释
 */

/**
 * 文档注释
 */

```
```python
# 单行注释

'''
多行注释
'''

"""
多行注释
"""
```

### 声明变量
```rust
// 加了mut才是意义上的变量
let mut number = 7;
// 不能被重新赋值的变量
let symbol = "abc";
// 指定类型
let x: i32 = 1;
let f: bool = true;

```
```java
int number = 7;
int x = 1;
boolean f = true;
```
```python
number = 7
x = 1
f = True
```
### 声明常量
```rust
const VALUE = 100;
```
```java
final int VALUE = 100;
```
```python
# python没有常量的定义
VALUE = 100;
```

### 函数
```rust
fn method1() {
}

pub fn method2() -> i32 {
}

fn method3(x: i32) -> i64 {
}

pub fn method4(x: i32, y: bool) -> f64 {
}
```
```java
void method1() {
}

public int method2() {
}

long method3(int x) {
}

public double method4(int x, boolean y) {
}
```
```python
def method1():
    pass
def method2() -> int:
    pass
def method3(x: int) -> int:
    pass
def method4(x: int, y: bool) -> float:
    pass
# python有默认参数和关键字参数，而且其实并不需要声明返回值
def method(x=None, y=None):
    pass
```

### 类（结构体）
```rust
struct Person {
    age: i32,
    name: String,
}
```
```java
class Person {
    int age;
    String name;
}
```
```python
class Person(object):
    def __init__(self, age=None, name=None):
        self.age = age 
        self.name = name
```
### 带方法实现
```rust
struct Rectangle {
    width: i32,
    height: i32,
}

impl Rectangle {
    fn area(&self) -> i32 {
        self.width * self.height
    }
    
    fn create(size: i32) -> Rectangle {
        Rectangle { width: size, height: size }
    }
}
fn main() {
    let rec1 = Rectangle::create(5);
    // 25
    println!(rec1.area()); 
}
```
```java
class Rectangle {
    int width;
    int height;
    
    Rectangle(int width, int height) {
        this.width = width;
        this.height = height;
    }
    
    int area() {
        return this.width * this.height;
    }
    
    static Rectangle create(int size) {
        return new Rectangle(size, size);
    }
}
public static void main(String[] args) {
    Rectangle rec1 = Rectangle.create(5);
    // 25
    System.out.println(rec1.area()); 
}
```
```python
class Rectangle(object):
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def area():
        return self.width * self.height
        
    @staticmethod
    def create(size):
        return Rectangle(size, size)
        
if __name__ == '__main__':
    rec1 = Rectangle.create(5)
    # 25
    print(rec1.area())        

```