# Flutter_doc_CokBK_List_Work_with_long_lists
 https://docs.flutter.dev/cookbook/lists/long-lists
Work with long lists
====================

1.  [Cookbook](https://docs.flutter.dev/cookbook)
2.  [Lists](https://docs.flutter.dev/cookbook/lists)
3.  [Work with long lists](https://docs.flutter.dev/cookbook/lists/long-lists)

The standard [`ListView`](https://api.flutter.dev/flutter/widgets/ListView-class.html) constructor works well for small lists. To work with lists that contain a large number of items, it's best to use the [`ListView.builder`](https://api.flutter.dev/flutter/widgets/ListView/ListView.builder.html) constructor.

In contrast to the default `ListView` constructor, which requires creating all items at once, the `ListView.builder()` constructor creates items as they're scrolled onto the screen.

[](https://docs.flutter.dev/cookbook/lists/long-lists#1-create-a-data-source)1\. Create a data source
-----------------------------------------------------------------------------------------------------

First, you need a data source. For example, your data source might be a list of messages, search results, or products in a store. Most of the time, this data comes from the internet or a database.

For this example, generate a list of 10,000 Strings using the [`List.generate`](https://api.flutter.dev/flutter/dart-core/List/List.generate.html) constructor.

content_copy

```
List<String>.generate(10000, (i) => 'Item $i'),
```

[](https://docs.flutter.dev/cookbook/lists/long-lists#2-convert-the-data-source-into-widgets)2\. Convert the data source into widgets
-------------------------------------------------------------------------------------------------------------------------------------

To display the list of strings, render each String as a widget using `ListView.builder()`. In this example, display each String on its own line.

content_copy

```
ListView.builder(
  itemCount: items.length,
  prototypeItem: ListTile(
    title: Text(items.first),
  ),
  itemBuilder: (context, index) {
    return ListTile(
      title: Text(items[index]),
    );
  },
)
```

`\
`
