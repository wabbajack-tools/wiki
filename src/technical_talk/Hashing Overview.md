# Hashing Overview

## Hashing Algorithms

Wabbajack uses a programming concept known as "content hashing". File hashing is a rather common computer programming concept in which a file is reduced to a set of bytes of a set length. There are many different ways to hash a file, and they very in performance and what is known as the "collision chance". The "collision chance" is the likeliness that two files will hash to the same hash code even though the contents of those files are different. In Wabbajack we want to avoid hash collision as much as possible, as two different files hashing to the same code would be catastrophic.

A non-goal for the Wabbajack hashing routines is for them to be "secure". A secure hash algorithm goes to great lengths to make sure that a given code cannot be "decoded" into the original string. These secure (or cryptographic) hash codes are often used to store passwords in databases. With a secure hash, the hash of a password can be stored in a database, and if the database is compromised no harm is done as the user's password cannot be determined by the hash. Unfortunately these cryptographic hash routines are often orders of magnitude slower than non-cryptographic hash.

Several hash codes that you may see in the modding community are:

* `CRC` - Not really a hash code, but acts like one. It is only really useful for basic file consistency checks. It's often 32 bytes in length and has a very high hash collision chance (it's easy to make two hashes collide)
* `MD5` - A cryptographic hash, but not a very secure one. MD5 is used for historical reasons, but modern computers can brute-force a MD5 in about 30 minutes. MD5 also has some flaws that cause it to collide a lot, making it much less secure
* `SHA1` - A slightly better cryptographic hash, has been brute-forced in about 45 minutes
* `SHA256` - Takes a super computer to brute force, and it doesn't collide. However, the time required to calculate a `SHA256` of a large file makes it less than optimal for Wabbajack

As you can see, the best hashes mentioned above tend to be slow, and cryptographic (a feature Wabbajack doesn't require). Thankfully a few years back a developer by the name of Yann Collet (<https://github.com/Cyan4973>) realized that someone needed to make a hash algorithm that didn't collide, and was fast enough to be used to hash large multi-GB files (like videos), and so he made xxHash, and later xxHash64. xxHash64 has a very low hash collision rate, is not cryptographic, and runs almost at the speed of a computer's memory, and in our case that means the hashing rate is limited by the speed of the disk storage.

## Hash formatting (Base 64 vs Base 16)

Hash codes in almost any format are in the form of raw bytes of data. And yet in apps we need a way to make these bytes a bit more presentable to users. A common way of displaying hash codes is via hexadecimal numbers, for example "Cheese for Everyone!" might be displayed as: `b3584f423b8c21b871a0abce260259f58cb3657e03fb1121c674f170e990d35d`. While this format works well for displaying single codes, some files in Wabbajack may contain hundreds of thousands of hash codes. Therefore Wabbajack chooses to use base 64 encoding instead. Most numbers used by humans (like the number `42`) are written in base 10 format (10 values for a single digit place). Hexadecimal numbers are also known as "base 16" numbers as they include `a` through `f` as possible digit values. Base64 expands this with all the letters of the alphabet, lower and upper case, and some punctuation. Thus the xxHas64 code for "Cheese for Everyone!" in base 64 encoding is : `eSIyd+KOG3s=`