Base 256 Encoding using Unicode (B256U)
=======================================
This repo contains a simple C++ program to represent binary data in base 256 encoding using Unicode characters. Each Unicode character represents exactly one byte and vice versa: each byte is represented by exactly one Unicode character, e.g. byte 0 is represented by Unicode digit '0'.

Advantages
----------
* **it's short**: just 16 Unicode characters represent 128-bit of data, 32 characters represent 256-bit of data
* **it's safe**: people are forced to copy & paste it 
* **it's easy to implement**: see the [source code](base256.cpp)
* **it's easy to recognize**: lots of umlauts (see the examples below)
* **it supports double-click** for copy & paste (no terminal characters in B256U) 
* **it's backward compatible**: B256U uses Unicode 1.0 only (highest code point used is 385)

How does it work?
-----------------
The B256U alphabet of 256 possible Unicode characters consists of:

1. the **10 digits** (0...9)
2. the **26 uppercase letters** (A...Z) and the **26 lowercase letters** (a...z)
3. the **194 umlaut characters** (À, Á, Â, Ã, Ä, Å, ...)

Typical use cases for B256U encoding are safe passwords, file checksums, identifiers and hashes.

Build Requirements
------------------
Just cmake and a C++ compiler are required.

Installation
------------
Execute in a terminal window: 
```
> git clone https://github.com/fleschutz/base256unicode  # Or download und unzip the ZIP file (click green button)
> cd base256unicode
> cmake .
> make
> ./base256
```

Examples
--------
128-bit of random data in base 256: `ĺËĀ8Ę3ĩŔá0VzœĹŀî`, `ŽTĭŊõł3ÐÑęGųĢÛąĶ`, `5iŗ3īÛźUKĺŰÑÞbŒŜ`, `ņĨqvLŀŠsůØŸÙGCŰƀ`, `ŋôBĉOÍŬįēĳmōįUĞÜ`, `Sőś6ŬŹŠęűöìÇthTK`.

256-bit of random data in base 256: `ħŅŹĬšÝŋţĀĸĻňőċqâĮŹúŪßWPŞÓā8æťÁüċ`, `Ě2ħŤRŧáÃĆĶ2ÕŀSŜöĄPŞÜbŰ06lŔùö9ĬŒģ`, `āLë2lÏäöĥųŧpğĨķŇHĺ4LăsŸđĵ_űLeYhĩ`, `ÂŚÔJàįŶļcvàPĈčĲċĉĲĂūęŻÉĢJĸķ3ğPĭŠ`

How long does it take to break a random key or password?
--------------------------------------------------------
Trying every possible key or password (called a 'brute force attack') at one billion attempts per second:

| Key size | Time needed                               | Key example                        |
|----------|-------------------------------------------|------------------------------------|
|  40-bit  | about 9 minutes                           |                                    |
|  56-bit  | about a year                              |                                    |
| 128-bit  | about 5,783,128,169,837,158,197,871 years | `ĤŗwĹĦñŧīĳēaqöĜĖŅ`                 |
| 256-bit  | never, for all practical purposes         | `ÿőMêŽĖiĘśŃäŞŰÀ8ŒŽĎäPfSŖÔń÷Ī7ėëŷò` |

📧 Feedback
------------
Send your email feedback to: markus.fleschutz [at] gmail.com

🤝 License & Copyright
-----------------------
This open source project is licensed under the CC0 license. All trademarks are the property of their respective owners.
