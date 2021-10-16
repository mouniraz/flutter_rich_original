# flutter_rich_original

## Getting Started

This project is an example of starting point for learning to create a simple Flutter application.

## Steps

1. Delete  all the default code coming with the boilerplate except the `runApp()` method inside the `main()`.
```dart
import 'package:flutter/material.dart';

void main() => runApp();
```

2. Inside the `runApp()` method, call the `MaterialApp()` widget class with a `home:` property having `Scaffold()` class.
```dart
void main() {
  runApp(
    const MaterialApp(
      home: Scaffold(),
    ),
  );
}
```

3. Add an `AppBar()` widget to the `appBar` property of the `Scaffold()` and add a title property to it.
```dart
void main() {
  runApp(
    MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('I am rich'),
        ),
      ),
    ),
  );
}
```

4. Change the background color of the `AppBar` and the `Scaffold`.
```dart
void main() {
  runApp(
    MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        backgroundColor: Colors.blueGrey,
        appBar: AppBar(
          title: Text('I am rich'),
          backgroundColor: Colors.blueGrey[900],
        ),
      ),
    ),
  );
}
```

5. Add a `body` property to the `Scaffold()` widget that gets an `Image()` widget as a value.
   
6. Add an `image` proprty to the `Image()` widget that gets an `NetworkImage()` widget as a value.
```dart
void main() {
  runApp(
    MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        backgroundColor: Colors.blueGrey,
        appBar: AppBar(
          title: Text('I am rich'),
          backgroundColor: Colors.blueGrey[900],
        ),
        body: Image(
          image: NetworkImage('https://cdn.pixabay.com/photo/2015/04/19/08/32/marguerite-729510__340.jpg'),
        ),
      ),
    ),
  );
}
```

7. Align the image and the appBar title to the center.
```dart
void main() {
  runApp(
    MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        backgroundColor: Colors.blueGrey,
        appBar: AppBar(
          title: Center(child: Text('I am rich')),
          backgroundColor: Colors.blueGrey[900],
        ),
        body: Center(
          child: Image(
            image: NetworkImage('https://cdn.pixabay.com/photo/2015/04/19/08/32/marguerite-729510__340.jpg'),
          ),
        ),
      ),
    ),
  );
}
```

8. Create a folder *images* inside the root directory of the project and paste the `diamond.png` file inside it ([download file](https://raw.githubusercontent.com/houcem-h/i_am_rich_original/master/images/diamond.png?token=AFHVFFBYZUI3L6ISJRMI5JTBNPVHE)).
   
9. Open `pubspec.yml` file, and search for the `assets` section. Uncomment it, and add below it the path of the added image `- images/diamond.png`.
```yaml
  assets:
    - images/diamond.png
```

10. After saving the changes, we have to click on the `Pub get` command shortcut link in the right top corner of the `pubspec.yml` file.

11. Replace the `NetworkImage()` widget with a `AssetImage()` widget to get the `diamond.png` file.
```dart
void main() {
  runApp(
    MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        backgroundColor: Colors.blueGrey,
        appBar: AppBar(
          title: Center(child: Text('I am rich')),
          backgroundColor: Colors.blueGrey[900],
        ),
        body: Center(
          child: Image(
            image: AssetImage('images/diamond.png'),
          ),
        ),
      ),
    ),
  );
}
```

12. In order to get all the images inside the images folder we can update the `pubspec.yaml` configuration file by omitting the file name:
```yaml
  assets:
    - images/
```

13. Go to [app icon generator](https://appicon.co/) website and generate icons for *Android* and *iPhone*. Download and unzip the output file.

14. Replace the default icons by:
- for **Android**: inside the project folders tree, navigate to `android > app > src > main > res` and replace the `mipmap` folders by those unzipped in the previous step.
- for **iOS**: inside the project folders tree, navigate to `ios > Runner` and replace the `Assets.xcassets` folders by those unzipped in the previous step.
> make sure the icons are named `ic_launcher.png`
