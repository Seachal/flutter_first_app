# 给 Android 开发者的 Flutter 指南

## 如何更新 widgets？

在 Android 中，你可以直接操作更新 View。然而在 Flutter 中，Widget 是不可变的，无法被直接更新，你需要操作 Widget 的状态。

这就是有状态 (Stateful) 和无状态 (Stateless) Widget 概念的来源。StatelessWidget 如其字面意思—没有状态信息的 Widget。

这就是有状态 (Stateful) 和无状态 (Stateless) Widget 概念的来源。`StatelessWidget` 如其字面意思—没有状态信息的 Widget。

`StatelessWidget` 用于你描述的用户界面的一部分不依赖于除了对象中的配置信息以外的任何东西的场景。

例如在 Android 中，这就像显示一个展示图标的 `ImageView`。这个图标在运行过程中不会改变，所以在 Flutter 中就使用 `StatelessWidget`。

如果你想要根据 HTTP 请求返回的数据或者用户的交互来动态地更新界面，那么你就必须使用 `StatefulWidget`，并告诉 Flutter 框架 Widget 的`状态` (`State`) 更新了，以便 Flutter 可以更新这个 Widget。

这里需要着重注意的是，无状态和有状态的 Widget 本质上是行为一致的。它们每一帧都会重建，不同之处在于 `StatefulWidget` 有一个跨帧存储和恢复状态数据的 `State` 对象

如果你有疑问，那么记住这条规则：如果一个 Widget 会变化（例如由于用户交互），它是有状态的。然而，如果一个 Widget 响应变化，它的父 Widget 只要本身不响应变化，就依然是无状态的。如果你有疑问，那么记住这条规则：如果一个 Widget 会变化（例如由于用户交互），它是有状态的。然而，如果一个 Widget 响应变化，它的父 Widget 只要本身不响应变化，就依然是无状态的。


```
class SampleAppPage extends StatefulWidget {
  SampleAppPage({Key key}) : super(key: key);

  @override
  _SampleAppPageState createState() => _SampleAppPageState();
}

class _SampleAppPageState extends State<SampleAppPage> {
 
```

sca: `StatefulWidget` 持有  `State`,
`State` 有状态的界面。


## 如何布局 Widget？我的 XML 布局文件在哪里？

```
_getToggleChild() {
    if (toggle) {
      return Text('Toggle One');
    } else {
      return MaterialButton(onPressed: () {}, child: Text('Toggle Two'));
    }
  }
```

#Intents

#### [](https://flutter.cn/docs/get-started/flutter-for/android-devs#what-is-the-equivalent-of-an-intent-in-flutter)`Intent` 在 Flutter 中的对应概念是什么？

在 Android 中，`Intent` 主要有两个使用场景：在 Activity 之前进行导航，以及组件间通信。 Flutter 却没有 intent 这样的概念，但是你依然可以通过原生集成 ([插件](https://pub.flutter-io.cn/packages/android_intent)) 来启动 intent。

Flutter 实际上并没有 Activity 和 Fragment 的对应概念。在 Flutter 中你需要使用 `Navigator` 和 `Route` 在同一个 `Activity` 内的不同界面间进行跳转。