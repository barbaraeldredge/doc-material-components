# Buttons

[Buttons](https://material.io/components/buttons/) allow users to take actions, and make choices, with a single tap.

There are four types of buttons:

* [Text button](#text-button)
* [Outlined button](#outlined-button) 
* [Contained button](#contained-button)
* [Toggle button](#toggle-button)

<!-- TODO(b/1234568): Add example image here when it is available. -->

## [Text button](https://material.io/components/buttons/#text-button)

Text buttons are typically used for less-pronounced actions, including those located in dialogs and cards. In cards, text buttons help maintain an emphasis on card content.

### Text button example

Source code API:
* FlatButton
    * [Class definition](https://api.flutter.dev/flutter/material/FlatButton-class.html)
    * [GitHub source](https://github.com/flutter/flutter/blob/master/packages/flutter/lib/src/material/flat_button.dart)

The following example shows a text button with black text on a white background.

<img src="images/flutter-text.png" width="20%" alt="Text button example in Flutter showing the black text \'Flat Button\' over a white background.">

```dart
FlatButton(
  onPressed: () {
    /*...*/
  },
  child: Text(
    "Flat Button",
    style: TextStyle(fontSize: 20)
  ),
)
```

## [Outlined button](https://material.io/components/buttons/#outlined-button)

Outlined buttons are medium-emphasis buttons. They contain actions that are important, but aren’t the primary action in an app.

### Outlined button example

Source code API:

* OutlineButton
    * [Class definition](https://api.flutter.dev/flutter/material/OutlineButton-class.html)
    * [GitHub source](https://github.com/flutter/flutter/blob/master/packages/flutter/lib/src/material/outline_button.dart)

The following example shows an outlined button with black text on a white background surrounded by a gray outline.

<img src="images/flutter_outlined.png" alt="Outlined button example in Flutter with black text on a white background surrounded by a gray outline." width="20%">

```dart
OutlineButton(
  onPressed() {
    /*...*/
  },
  child: Text(
    "Outlined Button"
     style: TextStyle(fontSize: 20)

  ),
}
```


## [Contained button](https://material.io/components/buttons/#contained-button)

Contained buttons are high-emphasis, distinguished by their use of elevation and fill. They contain actions that are primary to your app.

### Contained button example

Source code API

* RaisedButton
    * [Class definition](https://api.flutter.dev/flutter/material/RaisedButton-class.html)
    * [GitHub source](https://github.com/flutter/flutter/blob/master/packages/flutter/lib/src/material/raised_button.dart)

The following example shows a contained button with black text on a gray background. Color schemes are typically determined by your theme.

<img src="images/flutter-contained.png" width="20%" alt="Contained button example in Flutter showing a button with black text on a gray background.">


```dart
RaisedButton(
    onPressed: () {},
    child: const Text(
         'Contained Button',
         style: TextStyle(fontSize: 20)
    ),
),

```

## [Toggle button](https://material.io/components/buttons/#toggle-button)

Toggle buttons can be used to group related options. To emphasize groups of related toggle buttons, a group should share a common container.

There are two types of toggle buttons:
* [Toggle bar](#toggle-bar)
* [Toggle icon button](#toggle-icon-button)

### Toggle bar

The toggle bar is a group of related toggle buttons sharing a common container.

#### Toggle bar example

Source code APIs:
* IconButton
    * [Class definition](https://api.flutter.dev/flutter/material/IconButton-class.html)
    * [GitHub source](https://github.com/flutter/flutter/blob/master/packages/flutter/lib/src/material/icon_button.dart)

The following example displays four `IconButton`s in a widget called `buildIconButton`. It uses another widget called `iconWidget` that allows users to toggle an `IconButton`: 

<img src="images/toggle_bar_screenshot_cropped.png" alt="Toggle bar example for Flutter displaying the following icons: aspect ratio, assignment, late assignment, and bookmark." width="30%">

```dart
class ToggleBarDemo extends StatefulWidget {
  ToggleBarDemo({Key key, this.title}) : super(key: key);

  final String title;

  @override
  _ToggleBarDemoState createState() => _ToggleBarDemoState();
}

class _ToggleBarDemoState extends State<ToggleBarDemo> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.title),
        actions: [
          IconButton(
              icon: const Icon(Icons.pages),
              tooltip: 'Change Page',
              onPressed: changePage),
        ],
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            buildIconButton(),
          ],
        ),
      ),
    );
  }

  /// The Routes were set in the main.dart. Navigator is a tool that lets you
  /// access these different routes.
  void changePage() {
    Navigator.of(context).pushReplacementNamed('/toggleIconPage');
  }

  List<bool> isSelected = List<bool>.filled(4, false);
  Widget buildIconButton() {
    return ToggleButtons(
      children: [
        Icon(Icons.aspect_ratio),
        Icon(Icons.assignment_ind),
        Icon(Icons.assignment_late),
        Icon(Icons.bookmark_border),
      ],
      onPressed: (int index) {
        setState(() {
          isSelected[index] = !isSelected[index];
        });
      },
      isSelected: isSelected,
    );
  }
}
```

### Toggle icon button

The toggle icon button allows you to select from a group using an icon. 

#### Toggle icon button example

Source code APIs:

* StatefulWidget
    * [Class definition](https://api.flutter.dev/flutter/widgets/StatefulWidget-class.html)
    * [GitHub source](<!-- unable to find source in GitHub -->)
* GestureDetector
    * [Class defintion](https://api.flutter.dev/flutter/widgets/GestureDetector-class.html)
    * [GitHub source](https://github.com/flutter/flutter/blob/master/packages/flutter/lib/src/widgets/gesture_detector.dart)
* GridTile
    * [Class definition](https://api.flutter.dev/flutter/material/GridTile-class.html)
    * [GitHub source](https://github.com/flutter/flutter/blob/master/packages/flutter/lib/src/material/grid_tile.dart)
* GridTileBar
    * [Class definition](https://api.flutter.dev/flutter/material/GridTileBar-class.html)
    * [GitHub source](https://github.com/flutter/flutter/blob/master/packages/flutter/lib/src/material/grid_tile_bar.dart)
* IconButton
    * [Class definition](https://api.flutter.dev/flutter/material/IconButton-class.html)
    * [GitHub source](https://github.com/flutter/flutter/blob/master/packages/flutter/lib/src/material/icon_button.dart)
* IconData
    * [Class defintion](https://api.flutter.dev/flutter/widgets/IconData-class.html)
    * [GitHub source](https://github.com/flutter/flutter/blob/master/packages/flutter/lib/src/widgets/icon_data.dart)

The following example shows four images arranged in a two-by-two array with a favorite icon in the upper-right corner of each image.

The photos and icon buttons are contained within instances of `GridDemoPhotoItem`, which extends the `GridTile` API. `GridDemoPhotoItem` does the following:

* fits a passed image to `Photo` to the size specified in `GridView`. 
* sets the icon displayed to `on` (`favorite`) or `off` (`favorite_border`) and sets `IconData` as determined by a call to `GestureDetector`.
* sets the icon color to white as opposed to the default black

The `ToggleIconDemoState` class contains the the list of photos that become the backgrounds to the `GridDemoPhotoItem` tiles.

<img src="images/toggle_icon_screenshot_cropped.png" alt="Flutter toggle icon button example showing four images in an array with a favorite icon in the upper-right corner of each image." width="50%">

```dart
import 'package:flutter/material.dart';

typedef BannerTapCallback = void Function(Photo photo);

/// Each tile has a photo within it. The photo is used to toggle the
/// icon between on and off.
class Photo {
  Photo({
    this.assetName,
    this.isFavorite = false,
  });

  final String assetName;
  bool isFavorite;
  String get tag => assetName; // Assuming that all asset names are unique.
}

/// This class is each tile within the Grid. It represents the individual items
/// you see. A widget is stateless if we know that the file will not change.
class GridDemoPhotoItem extends StatelessWidget {
  GridDemoPhotoItem({
    Key key,
    @required this.photo,
    @required this.onBannerTap,
  })  : assert(onBannerTap != null),
        super(key: key);

  final Photo photo;
  final BannerTapCallback
      onBannerTap; // User taps on the photo's header or footer.

  @override
  Widget build(BuildContext context) {
    final Widget image = GestureDetector(
      child: Hero(
        key: Key(photo.assetName),
        tag: photo.tag,
        child: Image.asset(
          photo.assetName,
          fit: BoxFit.cover,
        ),
      ),
    );

    final IconData icon =
        photo.isFavorite ? Icons.favorite : Icons.favorite_border;

    return GridTile(
        header: GestureDetector(
          onTap: () {
            onBannerTap(photo);
          },
          child: GridTileBar(
            leading: Icon(
              icon,
              color: Colors.white,
            ),
          ),
        ),
        child: image);
  }
}

/// Toggle Icon Demo is a stateful widget because it is not immutable meaning
/// that the Widget can change State. This widget is changing state each time
/// the user clicks on the Flutter Favorite Icon. Each time the user clicks on
/// that icon this page will build again. This is the reason this class has to
/// extend Stateful Widget.
class ToggleIconDemo extends StatefulWidget {
  ToggleIconDemo({Key key, this.title}) : super(key: key);

  final String title;
  @override
  ToggleIconDemoState createState() => ToggleIconDemoState();
}

class ToggleIconDemoState extends State<ToggleIconDemo> {
  List<Photo> photos = <Photo>[
    Photo(assetName: 'assets/images/img1.jpg'),
    Photo(assetName: 'assets/images/img2.jpg'),
    Photo(assetName: 'assets/images/img3.jpg'),
    Photo(assetName: 'assets/images/img4.jpg'),
  ];

  void changePage() {
    Navigator.of(context).pushReplacementNamed('/toggleBarPage');
  }

  @override
  Widget build(BuildContext context) {
    final Orientation orientation = MediaQuery.of(context).orientation;
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.title),
        actions: [
          IconButton(
              icon: const Icon(Icons.pages),
              tooltip: 'Change Page',
              onPressed: changePage),
        ],
      ),
      body: Column(
        children: [
          Expanded(
            child: SafeArea(
              top: false,
              bottom: false,
              child: GridView.count(
                crossAxisCount: (orientation == Orientation.portrait) ? 2 : 3,
                mainAxisSpacing: 4.0,
                crossAxisSpacing: 4.0,
                padding: const EdgeInsets.all(4.0),
                childAspectRatio:
                    (orientation == Orientation.portrait) ? 1.0 : 1.3,
                children: photos.map<Widget>((Photo photo) {
                  return GridDemoPhotoItem(
                    photo: photo,
                    onBannerTap: (Photo photo) {
                      setState(() {
                        photo.isFavorite = !photo.isFavorite;
                      });
                    },
                  );
                }).toList(),
              ),
            ),
          ),
        ],
      ),
    );
  }
}
 ```
