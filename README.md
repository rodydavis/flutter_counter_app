# Flutter Counter App

A simple and elegant counter application built with Flutter. This app serves as a great starting point for anyone new to Flutter, demonstrating the basics of building a user interface and managing state.

<a href="https://studio.firebase.google.com/import?url=https%3A%2F%2Fgithub.com%2Frodydavis%2Fflutter_counter_app">
  <img
    height="32"
    alt="Try in Firebase Studio"
    src="https://cdn.firebasestudio.dev/btn/try_blue_32.svg">
</a>

## 🚀 Features

*   **Simple Counter:** A clean and intuitive interface with a floating action button to increment the counter.
*   **State Management:** Demonstrates basic state management in Flutter using `setState`.
*   **Material Design:** Built with Google's Material Design principles for a beautiful and responsive user experience.

## 🏃 How to Run

1.  **Prerequisites:** Make sure you have the [Flutter SDK](https://flutter.dev/docs/get-started/install) installed.
2.  **Clone the repository:**
```bash
git clone https://github.com/rodydavis/flutter_counter_app.git
cd flutter_counter_app
```
3.  **Install dependencies:**
```bash
flutter pub get
```
4.  **Run the app:**
```bash
flutter run
```

## 🛠️ Built With

*   [Flutter](https://flutter.dev/) - The UI toolkit for building beautiful, natively compiled applications for mobile, web, and desktop from a single codebase.
*   [Dart](https://dart.dev/) - The programming language used by Flutter.

## 🤔 Understanding the Code

The application is built around a few key concepts in Flutter:

### `main()` function and `MyApp` widget

The execution of the app starts in the `main()` function, which runs the `MyApp` widget. `MyApp` is a `StatelessWidget` that sets up the application's title, theme, and home page.

```dart
import '''package:flutter/material.dart''';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
      ),
      home: const MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}
```

### `MyHomePage` widget and state

The `MyHomePage` widget is a `StatefulWidget`, meaning it can hold mutable state. The state is managed by the `_MyHomePageState` class. The `_counter` variable holds the current count.

```dart
class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;

  // ...
}
```

### `_incrementCounter()` method and `setState()`

The `_incrementCounter()` method is called when the floating action button is pressed. It increments the `_counter` variable and calls `setState()`. `setState()` tells the Flutter framework that the state has changed, which triggers a rebuild of the widget tree.

```dart
  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }
```

### `build()` method and widget tree

The `build()` method is where the UI is constructed. It returns a `Scaffold` widget, which provides the basic structure of the app (app bar, body, floating action button). The body of the `Scaffold` contains a `Column` widget that displays the counter text.

```dart
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.title),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            const Text('You have pushed the button this many times:'),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: const Icon(Icons.add),
      ),
    );
  }
```
