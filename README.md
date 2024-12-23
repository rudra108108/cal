import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Online Shop',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: HomePage(),
    );
  }
}

class HomePage extends StatelessWidget {
  final List<Map<String, String>> products = [
    {'name': 'T-shirt', 'price': '500', 'image': 'https://via.placeholder.com/150'},
    {'name': 'Shoes', 'price': '1500', 'image': 'https://via.placeholder.com/150'},
    {'name': 'Watch', 'price': '2000', 'image': 'https://via.placeholder.com/150'},
  ];

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Online Shop'),
      ),
      body: ListView.builder(
        itemCount: products.length,
        itemBuilder: (context, index) {
          return Card(
            margin: EdgeInsets.all(10),
            child: ListTile(
              leading: Image.network(products[index]['image']!),
              title: Text(products[index]['name']!),
              subtitle: Text('Price: ৳${products[index]['price']}'),
              trailing: ElevatedButton(
                onPressed: () {
                  // Add to cart functionality here
                },
                child: Text('Buy'),
              ),
            ),
          );
        },
      ),
    );
  }
}
