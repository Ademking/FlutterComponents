# Code

```
import 'package:flutter/material.dart';

class NetworkGiffyDialog extends StatelessWidget {
  final Widget image;
  final Text title;
  final Text description;
  final bool onlyOkButton;
  final Text buttonOkText;
  final Text buttonCancelText;
  final Color buttonOkColor;
  final Color buttonCancelColor;
  final double buttonRadius;
  final double cornerRadius;
  final VoidCallback onOkButtonPressed;

  NetworkGiffyDialog({
    Key key,
    @required this.image,
    @required this.title,
    @required this.onOkButtonPressed,
    this.description,
    this.onlyOkButton = false,
    this.buttonOkText,
    this.buttonCancelText,
    this.buttonOkColor,
    this.buttonCancelColor,
    this.cornerRadius = 8.0,
    this.buttonRadius = 8.0,
  })  : assert(image != null),
        assert(title != null),
        super(key: key);

  @override
  Widget build(BuildContext context) {
    return Dialog(
      shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(cornerRadius)),
      child: Container(
        height: MediaQuery.of(context).size.height * 0.6,
        width: MediaQuery.of(context).size.width * 0.8,
        child: Column(
          mainAxisAlignment: MainAxisAlignment.spaceBetween,
          children: <Widget>[
            Column(
              children: <Widget>[
                Container(
                  width: MediaQuery.of(context).size.width * 0.8,
                  height: (MediaQuery.of(context).size.height / 2) * 0.6,
                  child: Card(
                    elevation: 0.0,
                    margin: EdgeInsets.all(0.0),
                    shape: RoundedRectangleBorder(
                        borderRadius: BorderRadius.only(
                            topRight: Radius.circular(cornerRadius),
                            topLeft: Radius.circular(cornerRadius))),
                    clipBehavior: Clip.antiAlias,
                    child: image,
                  ),
                ),
                Padding(
                  padding: const EdgeInsets.only(top: 16.0),
                  child: title,
                ),
                Padding(
                  padding: const EdgeInsets.all(8.0),
                  child: description,
                ),
              ],
            ),
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: Row(
                mainAxisAlignment: !onlyOkButton
                    ? MainAxisAlignment.spaceEvenly
                    : MainAxisAlignment.center,
                children: <Widget>[
                  !onlyOkButton
                      ? RaisedButton(
                          color: buttonCancelColor ?? Colors.grey,
                          shape: RoundedRectangleBorder(
                              borderRadius:
                                  BorderRadius.circular(buttonRadius)),
                          onPressed: () => Navigator.of(context).pop(),
                          child: buttonCancelText ??
                              Text(
                                'Cancel',
                                style: TextStyle(color: Colors.white),
                              ),
                        )
                      : Container(),
                  RaisedButton(
                    color: buttonOkColor ?? Colors.green,
                    shape: RoundedRectangleBorder(
                        borderRadius: BorderRadius.circular(buttonRadius)),
                    onPressed: onOkButtonPressed ?? () {},
                    child: buttonOkText ??
                        Text(
                          'OK',
                          style: TextStyle(color: Colors.white),
                        ),
                  ),
                ],
              ),
            ),
          ],
        ),
      ),
    );
  }
}



class AssetGiffyDialog extends StatelessWidget {
  final Image image;
  final Text title;
  final Text description;
  final bool onlyOkButton;
  final Text buttonOkText;
  final Text buttonCancelText;
  final Color buttonOkColor;
  final Color buttonCancelColor;
  final double buttonRadius;
  final double cornerRadius;
  final VoidCallback onOkButtonPressed;

  AssetGiffyDialog({
    Key key,
    @required this.image,
    @required this.title,
    @required this.onOkButtonPressed,
    this.description,
    this.onlyOkButton = false,
    this.buttonOkText,
    this.buttonCancelText,
    this.buttonOkColor,
    this.buttonCancelColor,
    this.cornerRadius = 8.0,
    this.buttonRadius = 8.0,
  })  : assert(image != null),
        assert(title != null),
        super(key: key);

  @override
  Widget build(BuildContext context) {
    return Dialog(
      shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(cornerRadius)),
      child: Container(
        height: MediaQuery.of(context).size.height * 0.6,
        width: MediaQuery.of(context).size.width * 0.8,
        child: Column(
          mainAxisAlignment: MainAxisAlignment.spaceBetween,
          children: <Widget>[
            Column(
              children: <Widget>[
                Container(
                  width: MediaQuery.of(context).size.width * 0.8,
                  height: (MediaQuery.of(context).size.height / 2) * 0.6,
                  child: Card(
                    elevation: 0.0,
                    margin: EdgeInsets.all(0.0),
                    shape: RoundedRectangleBorder(
                        borderRadius: BorderRadius.only(
                            topRight: Radius.circular(cornerRadius),
                            topLeft: Radius.circular(cornerRadius))),
                    clipBehavior: Clip.antiAlias,
                    child: image,
                  ),
                ),
                Padding(
                  padding: const EdgeInsets.only(top: 16.0),
                  child: title,
                ),
                Padding(
                  padding: const EdgeInsets.all(8.0),
                  child: description,
                ),
              ],
            ),
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: Row(
                mainAxisAlignment: !onlyOkButton
                    ? MainAxisAlignment.spaceEvenly
                    : MainAxisAlignment.center,
                children: <Widget>[
                  !onlyOkButton
                      ? RaisedButton(
                          color: buttonCancelColor ?? Colors.grey,
                          shape: RoundedRectangleBorder(
                              borderRadius:
                                  BorderRadius.circular(buttonRadius)),
                          onPressed: () => Navigator.of(context).pop(),
                          child: buttonCancelText ??
                              Text(
                                'Cancel',
                                style: TextStyle(color: Colors.white),
                              ),
                        )
                      : Container(),
                  RaisedButton(
                    color: buttonOkColor ?? Colors.green,
                    shape: RoundedRectangleBorder(
                        borderRadius: BorderRadius.circular(buttonRadius)),
                    onPressed: onOkButtonPressed ?? () {},
                    child: buttonOkText ??
                        Text(
                          'OK',
                          style: TextStyle(color: Colors.white),
                        ),
                  ),
                ],
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```

# How to use

```
import 'package:flutter/material.dart';
import 'package:giffy_dialog/giffy_dialog.dart';

void main() => runApp(new MyApp());

const List<Key> keys = [
  Key("Network"),
  Key("NetworkDialog"),
  Key("Flare"),
  Key("FlareDialog"),
  Key("Asset"),
  Key("AssetDialog")
];

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'Giffy Dialog Demo',
      theme: ThemeData(primarySwatch: Colors.teal, fontFamily: 'Nunito'),
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Giffy Dialog Example'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            RaisedButton(
                key: keys[0],
                color: Colors.teal,
                child: Text(
                  'Network Giffy',
                  style: TextStyle(
                    color: Colors.white,
                  ),
                ),
                onPressed: () {
                  showDialog(
                      context: context,
                      builder: (_) => NetworkGiffyDialog(
                            key: keys[1],
                            image: Image.network(
                              "https://raw.githubusercontent.com/Shashank02051997/FancyGifDialog-Android/master/GIF's/gif14.gif",
                              fit: BoxFit.cover,
                            ),
                            title: Text(
                              'Granny Eating Chocolate',
                              textAlign: TextAlign.center,
                              style: TextStyle(
                                  fontSize: 22.0, fontWeight: FontWeight.w600),
                            ),
                            description: Text(
                              'This is a granny eating chocolate dialog box. This library helps you easily create fancy giffy dialog.',
                              textAlign: TextAlign.center,
                            ),
                            onOkButtonPressed: () {},
                          ));
                }),
            RaisedButton(
                key: keys[2],
                color: Colors.teal,
                child: Text(
                  'Flare Giffy',
                  style: TextStyle(
                    color: Colors.white,
                  ),
                ),
                onPressed: () {
                  showDialog(
                      context: context,
                      builder: (_) => FlareGiffyDialog(
                            key: keys[3],
                            flarePath: 'assets/space_demo.flr',
                            flareAnimation: 'loading',
                            title: Text(
                              'Space Reloading',
                              style: TextStyle(
                                  fontSize: 22.0, fontWeight: FontWeight.w600),
                            ),
                            description: Text(
                              'This is a space reloading dialog box. This library helps you easily create fancy flare dialog.',
                              textAlign: TextAlign.center,
                              style: TextStyle(),
                            ),
                            onOkButtonPressed: () {},
                          ));
                }),
            RaisedButton(
                key: keys[4],
                color: Colors.teal,
                child: Text(
                  'Asset Giffy',
                  style: TextStyle(
                    color: Colors.white,
                  ),
                ),
                onPressed: () {
                  showDialog(
                      context: context,
                      builder: (_) => AssetGiffyDialog(
                            key: keys[5],
                            image: Image.asset(
                              'assets/men_wearing_jacket.gif',
                              fit: BoxFit.cover,
                            ),
                            title: Text(
                              'Men Wearing Jackets',
                              style: TextStyle(
                                  fontSize: 22.0, fontWeight: FontWeight.w600),
                            ),
                            description: Text(
                              'This is a men wearing jackets dialog box. This library helps you easily create fancy giffy dialog.',
                              textAlign: TextAlign.center,
                              style: TextStyle(),
                            ),
                            onOkButtonPressed: () {},
                          ));
                }),
          ],
        ),
      ),
    );
  }
}
```
