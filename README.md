# Secure string
This is a cryptographically secure random string generator based on `dart:math.Random.secure`.

## Usage:
Create an instance with `new SecureString()`:
```Dart
SecureString secureString = new SecureString();
```

Then generate random strings with it:
```Dart
String randomString = secureString.generate(length: 512);
```
The length defaults to `1024` if no length is specified.

### Custom character lists
To specify a list of allowed characters, use the named parameter `charList`:
```Dart
String randomBinaryString = secureString.generate(charList: ["0", "1"]);
```
The list defaults to hexadecimal characters (0-f).

### Insecure string:
To create insecure random strings: use `new SecureString(string: false)` instead of `new SecureString()`. You can also specify a seed using `new SecureString(string: false, seed: 2)` (replacing 2 with your seed).

## Trivia:
This library was made in spite of a [library already existing](https://github.com/damondouglas/random_string.dart) due to two reasons:
- That library did not have functionality for `Random.secure`.
- That library was licensed under the BSD 3 clause license.
