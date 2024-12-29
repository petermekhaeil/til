# Dart Supports Underscore Digit Separators

In Dart (starting from version 3.6.0), you can use underscores (`_`) as digit separators in number literals to make them more readable. This is especially handy for large numbers or when grouping digits for higher-level clarity.

Here are some examples:

```dart
var n1 = 1_000_000;
var n2 = 0.000_000_000_01;
var n3 = 0x00_14_22_01_23_45;  // MAC address
var n4 = 65_1234_5678;  // SG Phone number
var n5 = 100__000_000__000_000;  // one hundred million million!
```

This feature makes it easier to read long numeric values and organize digits meaningfully.

Dart isn’t alone in supporting this - other languages like JavaScript, Java, Python, and Kotlin also allow underscore digit separators. It's a great example of a feature that crosses language boundaries to make code cleaner and more human-readable.
