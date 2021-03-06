# flutter_slidable

A Flutter implementation of slidable list item with left and right slide actions.

[![Pub](https://img.shields.io/pub/v/flutter_slidable.svg)](https://pub.dartlang.org/packages/flutter_slidable)
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=QTT34M25RDNL6)

![Overview](https://raw.githubusercontent.com/letsar/flutter_slidable/master/doc/images/slidable_overview.gif)

## Features

* Accepts left and right widget lists as slide actions.
* 4 built-in layouts.
* 2 built-in slide action widget.
* You can easily create you custom layouts and animations.
* You can use a builder to create your slide actions if you want special effects during animation.

## Getting started

In the `pubspec.yaml` of your flutter project, add the following dependency:

```yaml
dependencies:
  ...
  flutter_slidable: "^0.2.0"
```

In your library add the following import:

```dart
import 'package:flutter_slidable/flutter_slidable.dart';
```

For help getting started with Flutter, view the online [documentation](https://flutter.io/).

### Constructors
You can create a `Slidable` in two different ways:
* By calling the `Slidable` constructor and passing a list of slide actions.
* By calling the `Slidable.builder` constructor and passing slide action builders, if you want special effects during the animation.

A `Slidable` needs multiple things:

* Slide actions (see below for details). Which can be any widget. For convenience this package has 2 built-in side action widgets.
* A delegate. This is what controls the layout and the animation of the slide menu.
* An extent ratio between a slide action extent and the item extent.
* A child.

The `actions` contains the slide actions that appears when the child has been dragged down or to the right.
The `secondaryActions` contains the slide actions that appears when the child has been dragged up or to the left.

A `direction` parameter let you choose if you want actions to appear when you slide horizontally or vertically (horizontally by default).

```dart
new Slidable(
  key: Key('$3'),
  delegate: new SlidableDrawerDelegate(),
  actionExtentRatio: 0.25,
  child: new Container(
    color: Colors.white,
    child: new ListTile(
      leading: new CircleAvatar(
        backgroundColor: Colors.indigoAccent,
        child: new Text('$3'),
        foregroundColor: Colors.white,
      ),
      title: new Text('Tile n°$3'),
      subtitle: new Text('SlidableDrawerDelegate'),
    ),
  ),
  actions: <Widget>[
    new IconSlideAction(
      caption: 'Archive',
      color: Colors.blue,
      icon: Icons.archive,
      onTap: () => _showSnackBar('Archive'),
    ),
    new IconSlideAction(
      caption: 'Share',
      color: Colors.indigo,
      icon: Icons.share,
      onTap: () => _showSnackBar('Share'),
    ),
  ],
  secondaryActions: <Widget>[
    new IconSlideAction(
      caption: 'More',
      color: Colors.black45,
      icon: Icons.more_horiz,
      onTap: () => _showSnackBar('More'),
    ),
    new IconSlideAction(
      caption: 'Delete',
      color: Colors.red,
      icon: Icons.delete,
      onTap: () => _showSnackBar('Delete'),
    ),
  ],
);
```

### Built-in slide actions

This package comes with 2 kind of slide actions:

* `SlideAction` which the more permissive. You can choose a background color, or any decoration, and it takes any widget as a child.
* `IconSlideAction` which requires an icon, and cake have a background color and a caption below the icon.

### Built-in delegates

This package comes with 4 kind of delegates:

#### SlidableBehindDelegate

The slide actions stay behind the item while it's sliding:

![Overview](https://raw.githubusercontent.com/letsar/flutter_slidable/master/doc/images/slidable_behind.gif)

#### SlidableScrollDelegate

The slide actions follow the item while it's sliding:

![Overview](https://raw.githubusercontent.com/letsar/flutter_slidable/master/doc/images/slidable_scroll.gif)

#### SlidableDrawerDelegate

The slide actions which animate like drawers while the item is sliding:

![Overview](https://raw.githubusercontent.com/letsar/flutter_slidable/master/doc/images/slidable_drawer.gif)

#### SlidableStrechDelegate

The slide actions stretch while the item is sliding:

![Overview](https://raw.githubusercontent.com/letsar/flutter_slidable/master/doc/images/slidable_stretch.gif)

## Changelog

Please see the [Changelog](https://github.com/letsar/flutter_slidable/blob/master/CHANGELOG.md) page to know what's recently changed.

## Contributions

Feel free to contribute to this project.

If you find a bug or want a feature, but don't know how to fix/implement it, please fill an [issue](https://github.com/letsar/flutter_slidable/issues).  
If you fixed a bug or implemented a new feature, please send a [pull request](https://github.com/letsar/flutter_slidable/pulls).