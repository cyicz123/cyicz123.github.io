---
title: "Comparison of Java and C++"
date: 2020-09-20 13:35:13
tags:
	- 英语
	- 学习
categories:
	- [学习]
	- [英语]
comment: true
top: 1
---

## the similarities 

Java and C++ are object-oriented language which both go in with object-oriented mentality(encapsulation,inherit,polymorphism).Because object-oriented has many very good features,such as inherit,polymorphism,etc,Java and C++ have excellent reusability.

Java and C++ not only have the most similarity in object-oriented design mentality,but also are similar in the syntax. They have same keywords,such as `if for while const new`.Although they have too many similar in syntax and object-oriented mentality,there are lots of different between Java and C++ in kernel.

## the differences

Although Java and C++ all implement the object-oriented programming paradigm,there are lots of different between Java and C++ in kernel.

For example,C++ supports multi-inheritance,but Java doesn't.

So why does C++ support multi-inheritance，but Java doesn't?

Firstly,we should understand the diamond problem. Following this graph ,we assume that there are two derived class $ B_1,B_2 $ which derive from the base class A. Then class C derive from class B_1,B_2.

It has a member function display() in class A. So class C derive from the B_1 and B_2 ,has two same member function display().It's a question what the method display() should be called?

![img](https://pic4.zhimg.com/80/v2-b20fbc2d313495e9696d3fa29c260926_720w.jpg)

C++ use the domain qualifier or virtual base class to solve this problem.

```c++
class B1:public B0
class B2:public B0
class D:public B1,public B2// D d;d.display()  ERROR

class B1:virtual public B0
class B2:virtual public B0
class D:public B1,public B2// D d;d.display() no problem
```



But Java designer chose to delete this characteristic. There is a joke in the following.

The programmers in C++ designers' mind:

![img](https://pic3.zhimg.com/80/636ca241fb4ef4e14034768efd017a1c_1440w.jpg?source=1940ef5c)

The programmers in Java designers' mind:

![img](https://pic4.zhimg.com/80/cbd491e1286e83e3e933ad6658a35606_1440w.jpg?source=1940ef5c)

## the difference of compiling

C++ is the standard representative that write once and then compile anywhere(WOCA).

Conversely Java write once,run anywhere  due to JVM.

JVM is the abbreviation of Java Virtual Machine, which is achieved by simulating various computer functions on an actual computer. It's constructed by a bitecode Instruction set,a register,a stack,a garbage collection heap,and a storage method field. JVM shields information related to the operating system platform, so that Java programs only need to generate object code (bytecode) that runs on the JVM, and can run on multiple platforms without modification. It's the reason that write once,run anywhere.

But precisely because of this,In addition to running a compiled Java program, computers running Java applications generally must also run the JVM, while compiled C++ programs can be run without external applications. Early versions of Java were significantly outperformed by statically compiled languages such as C++. This is because the program statements of these two closely related languages may compile to a few machine instructions with C++, while compiling into several byte codes involving several machine instructions each when interpreted by a JVM. 

## Paradigm

There are some paradigms.

* Imperative paradigm

* Procedural paradigm

* Declarative paradigm

* Functional paradigm

* Logic paradigm

* Object-oriented paradigm

Java is a multi-paradigm language. It mainly supports programming functions based on object-oriented, procedural and functional paradigms.At this point, I feel that there is no difference between C++ and Java.

