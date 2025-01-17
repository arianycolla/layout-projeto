# layout-projeto
import 'package:flutter/material.dart';

void main() {
  runApp(MeuApp());
}

class MeuApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Demonstração Flutter',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: MinhaPaginaInicial(),
    );
  }
}

class MinhaPaginaInicial extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Layout Responsivo'),
      ),
      body: LayoutBuilder(
        builder: (context, constraints) {
          if (constraints.maxWidth < 600) {
            return Column(
              children: [
                Container(color: Colors.red, height: 100, width: constraints.maxWidth),
                Container(color: Colors.green, height: 100, width: constraints.maxWidth),
              ],
            );
          } else {
            return Row(
              children: [
                Container(color: Colors.red, height: 100, width: constraints.maxWidth / 2),
                Container(color: Colors.green, height: 100, width: constraints.maxWidth / 2),
              ],
            );
          }
        },
      ),
    );
  }
}
