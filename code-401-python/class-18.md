# Cryptography

## Encryption, Decryption, and Cracking

[Source: Khan Academy](https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:online-data-security/xcae6f4a7ff015e7d:data-encryption-techniques/a/encryption-decryption-and-code-cracking)

The Caesar Cipher is one of the oldest encryption techniques.

It involves shifting the alphabet a certain number of times to one direction or the other, so that each letter actually represents another.

SECRET MEETING AT THE PALACE

Shifted 6 times comes out to

YKIXKZ SKKZOTM GZ ZNK VGRGIK

The shifted message appears to be completely unreadable, but if you know the shift that encoded it, decoding is easy.

According to records Caesar always used a shift of 3, but in the case that the shift is unknown, cracking the cipher is entirely possible using one of three methods.

* **Frequency Analysis** - Human languages use some letters more than others. Armed with this knowledge we can chart the frequency of characters in a cipher to decode certain most used letters like "E".
* **Known plaintext** - If part of the decoded message is already known, it can be used to decode an encrypted message
* **Brute Force** - With a limited number of shifts in the Caesar Cipher, we could simply try all 25 possible shift ciphers. This is usually the slowest approach.

### Additional terms to know

* **Encryption** - scrambling data according to a secret key
* **Decryption** - recovering original data from scrambled data using a secret key
* **Code cracking** - uncovering original data without knowing the secret key

## More on The Caesar Cipher

[Source: Wikipedia - Caesar Cipher](https://en.wikipedia.org/wiki/Caesar_cipher)

Same information, but a little more dry.

The Caesar Cipher is a very simple encryption, and doesn't off any sort of communication security in the modern day.

Frequency analysis is the best approach to solving. Vowels will generally have the highest frequency, with E being the very top most often.

That said, modern computers can also make brute force decryption fast and easy.
