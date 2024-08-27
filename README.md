Base 256 Encoding using Unicode (B256U)
=======================================
This repo contains a small C++ program to represent binary data in base 256 encoding by using Unicode characters. Typical use cases are safe passwords, digital keys, file checksums, identifiers and hashes.

What is B256U?
---------------
Each byte is represented by exactly one Unicode character and vice versa each Unicode character represents exactly one byte. The mapping of Byte vs Unicode is quite simple:

| Byte       | Unicode             | Description           |
|------------|---------------------|-----------------------|
| 0 ... 9    | '0' ... '9'         | 10 digits             |
| 10 ... 35  | 'A' ... 'Z'         | 26 uppercase letters  |
| 36 ... 61  | 'a' ... 'z'         | 26 lowercase letters  |
| 62 ... 255 | 'À', 'Á', 'Â', ...  | 194 umlaut characters |

✔️ Advantages of B256U
-----------------------
* **It's short:** encode 128-bit of data with 16 Unicode characters only.
* **It's easy to recognize:** lots of umlauts, see the examples below.
* **It's safe to use:** nearly impossible to remember (due to umlauts), so people are forced to copy & paste it.
* **Supports copy & paste with double-clicking:** all Unicode characters are non-terminal ones.
* **It's easy to implement:** see the [source code in main.cpp](main.cpp)
* **Supports every Unicode version:** the highest code point is 385 only, so Unicode 1.0 or higher is required.

Examples of B256U
-----------------
128-bit of random data in B256U: `ĺËĀ8Ę3ĩŔá0VzœĹŀî`, `ŽTĭŊõł3ÐÑęGųĢÛąĶ`, `5iŗ3īÛźUKĺŰÑÞbŒŜ`, `ņĨqvLŀŠsůØŸÙGCŰƀ`, `ŋôBĉOÍŬįēĳmōįUĞÜ`, `Sőś6ŬŹŠęűöìÇthTK`.

256-bit of random data in B256U: `ħŅŹĬšÝŋţĀĸĻňőċqâĮŹúŪßWPŞÓā8æťÁüċ`, `Ě2ħŤRŧáÃĆĶ2ÕŀSŜöĄPŞÜbŰ06lŔùö9ĬŒģ`, `āLë2lÏäöĥųŧpğĨķŇHĺ4LăsŸđĵ_űLeYhĩ`, `ÂŚÔJàįŶļcvàPĈčĲċĉĲĂūęŻÉĢJĸķ3ğPĭŠ`


🔧 Installation
----------------
Requires **cmake** and a **C++ compiler**. Then execute in a terminal window: 
```
> git clone https://github.com/fleschutz/base256  # or download und unzip the ZIP file (click the green button)
> cd base256
> cmake .
> make
> ./base256
```

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
