Base 256 Unicode (B256U) Encoding
=================================
This repo contains a simple C++ program to represent binary data in B256U encoding. Typical use cases for B256U are safe passwords, file checksums, identifiers and hashes.

What is B256U Encoding?
-----------------------
Each Unicode character represents exactly one byte (and vice versa: each byte is represented by one Unicode character) - dead simple. The B256U alphabet of 256 possible Unicode characters consists of:

1. the **10 digits** (0...9)
2. the **26 uppercase letters** (A...Z) and the **26 lowercase letters** (a...z)
3. the **194 umlaut characters** (À, Á, Â, Ã, Ä, Å, ...)

Advantages of B256U Encoding
----------------------------
* **it's short**: just 16 Unicode characters represent 128-bit of data, 32 characters represent 256-bit of data
* **it's safe**: people are forced to copy & paste it 
* **it's easy to implement**: see the [source code](base256.cpp)
* **it's easy to recognize**: lots of umlauts (see the samples below)
* **it supports double-click** for copy & paste (no terminal characters in B256U) 
* **it's backward compatible**: B256U uses Unicode 1.0 only (highest code point used is 385)

Installation
------------
Just a C++ compiler, git, and cmake is needed. Then execute in a terminal window:

```
> git clone https://github.com/fleschutz/base256unicode; cd base256unicode
> cmake .
> make
> ./base256
```

Samples of pseudo-random 128 bits encoded in B256U
--------------------------------------------------
* `ĺËĀ8Ę3ĩŔá0VzœĹŀî`
* `ŽTĭŊõł3ÐÑęGųĢÛąĶ`
* `5iŗ3īÛźUKĺŰÑÞbŒŜ`
* `ņĨqvLŀŠsůØŸÙGCŰƀ`

Samples of pseudo-random 256 bits encoded in B256U
--------------------------------------------------
* `ħŅŹĬšÝŋţĀĸĻňőċqâĮŹúŪßWPŞÓā8æťÁüċ`
* `Ě2ħŤRŧáÃĆĶ2ÕŀSŜöĄPŞÜbŰ06lŔùö9ĬŒģ`
* `āLë2lÏäöĥųŧpğĨķŇHĺ4LăsŸđĵ_űLeYhĩ`
* `ÂŚÔJàįŶļcvàPĈčĲċĉĲĂūęŻÉĢJĸķ3ğPĭŠ`

How long does it take to break a random key or password?
--------------------------------------------------------
Trying every possible key or password (called a 'brute force attack') at one billion attempts per second:

* a 40-bit key will be broken in about 9 minutes.
* a 56-bit key will be broken in about a year.
* a 128-bit key will be broken in about 5,783,128,169,837,158,197,871 years.
* a 256-bit key will never be broken, for all practical purposes.

Feedback
--------
Send your email feedback to: markus.fleschutz [at] gmail.com

License & Copyright
-------------------
This open source project is licensed under the CC0 license. All trademarks are the property of their respective owners.
