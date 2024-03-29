如果此项目能帮助到你，就请你给[一颗星](https://github.com/chenxing640/dart_crypto)，谢谢！(If this project can help you, please give it a [star](https://github.com/chenxing640/dart_crypto), thanks!)


[![License MIT](https://img.shields.io/badge/license-MIT-green.svg?style=flat)](LICENSE)&nbsp;
[![Support](https://img.shields.io/badge/support-iOS%20|%20Android-blue.svg?style=flat)](https://flutterchina.club)&nbsp;


## dart_crypto

<!-- 基于flutter_macos_v0.5.8-dev版本采用Dart语言开发。 -->
集成了Base64, 32/16 Bits MD5, AES, RSA等算法(This integrates Base64, 32/16 Bits MD5, AES and RSA algorithms.)。


## Group(ID:155353383)

<div align=left>
&emsp; <img src="https://github.com/chenxing640/dart_crypto/raw/master/images/qq155353383.jpg" width="30%" />
</div> 


## Getting Started

For help getting started with Flutter, view our online <br />

- [Flutter中文网](https://flutterchina.club) 
  - [Flutter文档](https://flutterchina.club/docs/)
  - [Flutter中文网开源项目](https://flutterchina.club/opensource.html)
  - [Flutter实战](https://book.flutterchina.club)

- [Flutter SDK releases](https://flutter.dev/docs/development/tools/sdk/releases#macos) - The Stable channel contains the most stable Flutter builds. See [Flutter’s channels](https://github.com/flutter/flutter/wiki/Flutter-build-release-channels) for details.

- [Flutter Samples](https://github.com/flutter/samples) - A collection of Flutter examples and demos.

- [Flutter Documentation](https://flutter.dev/docs)

- [FlutterHub](https://www.flutterhub.cn)

- [Dart packages](https://pub.flutter-io.cn) - Find and use packages to build [Dart↗](https://dart.cn/) and [Flutter↗](https://flutter.cn/) apps.

- [Dart API docs](https://api.flutter.dev) - The API reference herein covers all libraries that are exported by the Flutter SDK.

- [Dart 编程语言中文网](https://www.dartcn.com)

- [简单Dart示例 · Dart2 中文文档 · 看云](https://www.kancloud.cn/marswill/dark2_document/709087) - Dart2 语法、特性的讲解以及一些简单 Dart 示例参考。
  - *[A tour of the Dart language](https://www.dartlang.org/guides/language/language-tour) - 英文原版参考。*

- [DartPad](https://dartpad.dartlang.org/) - 使用 DartPad 来体验 Dart 语言的更多特性。


## Usage

### Plain Text

```dart
final plainText = "Lorem ipsum dolor sit amet, consectetur adipiscing elit ........。本文基本上是将dart官网部分内容进行翻译，没兴趣的请出门左转至Dart的官网，有兴趣的同志请继续阅读本文。Flutter教程在这里通常，映射是一个有键和值的对象。 键和值都可以是任何类型的对象。 每个键只出现一次，但您可以多次使用相同的值。Dart的Map支持由映射文字和Map。int和double都是num的子类型。 num类型包括基本运算符，如+， - ，/和*，也是你可以找到abs()，ceil()和floor()以及其他方法的地方。 （按位运算符，如>>，在int类中有定义。）如果num及其子类没有您要想要内容，那dart：math库可能有您想要的。Dart字符串是一系列UTF-16代码单元。 您可以使用单引号或双引号来创建字符串：您可以使用{expression}将表达式的值放在字符串中。如果表达式是标识符，则可以跳过{}。 要获取对应于对象的字符串，Dart调用对象的toString()方法。为了表示布尔值，Dart有一个名为bool的类型。 只有两个对象具有bool类型：true和false，它们都是编译时常量。Dart的类型安全意味着您不能使用if（nonbooleanValue）或assert（nonbooleanValue）等代码。 相反，明确检查值，如下所示：也许几乎每种编程语言中最常见的集合是数组或有序的对象组。 在Dart中，数组是List对象，因此大多数人只是将它们称为列表。Dart列表文字看起来像JavaScript数组文字。 这是一个简单的Dart List：";
```

### Base64

```dart
try {
    // Base64 - Encode
    final base64Encoded = crypto.DYFCryptoProvider.yf_base64Encode(plainText);
    print("[Base64] encode: " + base64Encoded);

    // Base64 - Dncode
    final base64Decoded = crypto.DYFCryptoProvider.yf_base64Decode(base64Encoded);
    print("[Base64] decode: " + base64Decoded);
} catch (e) {
    print("e: $e");
}
```

### MD5

```dart
try {
    // MD5 - 32 Bits Encode
    final md5Hash = crypto.DYFCryptoProvider.md5Encode(plainText);
    print("[MD5] Hash: " + md5Hash);

    // MD5 - 16 Bits Encode
    final md5b16hash = crypto.DYFCryptoProvider.bit16md5Enconde(plainText);
    print("[MD5] 16 Bits Hash: " + md5b16hash);
} catch (e) {
    print("e: $e");
}
```

### AES

```dart
try {
    // AES Key
    // final aesKey = "smMQI8dMK2nOMUR0TdpBYQUnLpbW8kjHrdy86WtU6eB1Ff6mYveYzezopmbjwBZEjPQmg";
    final aesKey = "smMQI8dMK2";
    print("[AES] key: " + aesKey);

    // AES - Encrypt
    String aesEncryptedText = crypto.DYFCryptoProvider.aesEncrypt(plainText, aesKey);
    print("[AES] encryptedText: " + aesEncryptedText);

    // AES - Decrypt
    String aesDecryptedText = crypto.DYFCryptoProvider.aesDecrypt(aesEncryptedText, aesKey);
    print("[AES] decryptedText: " + aesDecryptedText);
} catch (e) {
    print("e: $e");
}
```

### RSA

```
// 公钥
final publicKey =
"""MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCmPW2SwJFldGVB1SM82VYvSZYR
F1H5DREUiDK2SLnksxHAV/roC1uB44a4siUehJ9AKeV/g58pVrjhX3eSiBh9Khom
/S2hEWF2n/6+lqqiwQi1W5rjl86v+dI2F6NgbPFpfesrRjWD9uskT2VX/ZJuMRLz
8VPIyQOM9TW3PkMYBQIDAQAB""";

// 私钥 (pkcs8)
final privateKey =
"""MIICdgIBADANBgkqhkiG9w0BAQEFAASCAmAwggJcAgEAAoGBAKY9bZLAkWV0ZUHV
IzzZVi9JlhEXUfkNERSIMrZIueSzEcBX+ugLW4HjhriyJR6En0Ap5X+DnylWuOFf
d5KIGH0qGib9LaERYXaf/r6WqqLBCLVbmuOXzq/50jYXo2Bs8Wl96ytGNYP26yRP
ZVf9km4xEvPxU8jJA4z1Nbc+QxgFAgMBAAECgYArZVW5PXO3HE9ihBUSyVlqNrdp
9sB7VyHiTjuOwiVkwiocH9trv6s/mPmONVLjSJOZ2FYEl4Nw8yaIDrfUFJrvhdbh
HJnwkO27Wo5jEfm2qGCwgQNtUACoIH637LXfP81v5I7eZtEa7kfO8Axpp3czvO1H
dIAlOI8rU4jb3fB1cQJBANLgfHd/CDro1gtvTrUeTw/lqsKVScGiHn+pmT+THed6
ftJ2MAJVcL/0H8+fFN5mRypCL7LQyPO48dTmfY9PbocCQQDJz8xZGq2BNAd3gSrN
i3q++SEyjRPzDfr8AGJBJF8qtslcSYrVB/jjPx/qNNlMxOoXnpozBojzVTO3UirM
J/wTAkEAzb930YOhPREGHnwImFCtJT6ZYGcWYpXSGg8Y1d2tlLeA28myx+QjMTZ4
fzOgwemaz9FqBpcNKjctxOLqaRRAKwJAXPZwznbgh8zcx6rjea2PjFscdLnR/7tn
6x+OIy3K/NUYan+iCUHT33JblDpmAtwObXTs2SZgfZ645PBfsI2WqwJAGJxnG8+w
iCnzN0CIZvG96tfOZmz0lkM4NSHDwdCSbagJlZccOtodpn00Dzy+l0t+oFe0Xm3R
A0WkPzQX/seO0Q==""";
```

```dart
try {
    // RSA - Encrypt
    String rsaEncryptedText = crypto.DYFCryptoProvider.rsaEncrypt(plainText, publicKey);
    print("[rsa] encryptedText: " + rsaEncryptedText);

    // RSA - Decrypt
    String rsaDecryptedText = crypto.DYFCryptoProvider.rsaDecrypt(rsaEncryptedText, privateKey);
    print("[rsa] decryptedText: " + rsaDecryptedText);

    // RSA - Sign
    String signature = crypto.DYFCryptoProvider.rsaSign(plainText, privateKey);
    print("[rsa] signature: " + signature);

    // RSA - Verify
    bool ret = crypto.DYFCryptoProvider.rsaVerify(signature, plainText, publicKey);
    print("[rsa] signature verification: " + ret.toString());
} catch (e) {
    print("e: $e");
}
```


## Sample

- [string_utils.dart](https://github.com/chenxing640/dart_crypto/blob/master/lib/string_utils.dart)


## Other Project

- [grab_ethtoken_info](https://github.com/chenxing640/grab_ethtoken_info)


## Feedback is welcome

If you notice any issue, got stuck to create an issue. I will be happy to help you.
