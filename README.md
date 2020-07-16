# flutter_first_app

A new Flutter application.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

For help getting started with Flutter, view our
[online documentation](https://flutter.dev/docs), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

1. 在编写应用程序时，通常会创建新的widget，这些widget是无状态的StatelessWidget或者是有状态的StatefulWidget， 具体的选择取决于您的widget是否需要管理一些状态.

2. widget的主要工作是实现一个build函数，用以构建自身。

3. 一个widget通常由一些较低级别widget组成。Flutter框架将依次构建这些widget，直到构建到最底层的子widget时，这些最低层的widget通常为RenderObject，它会计算并描述widget的几何形状。
 > 依次构建， 从高级到低级？
 
 