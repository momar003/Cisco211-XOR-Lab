# Encryption/Decryption Using XOR

## Secret Message and Key

Plaintext message: **cat**
Secret key: **dog**

## ASCII and Binary Conversion

| Character | ASCII Decimal | Binary   |
| --------- | ------------: | -------- |
| c         |            99 | 01100011 |
| a         |            97 | 01100001 |
| t         |           116 | 01110100 |

| Key Character | ASCII Decimal | Binary   |
| ------------- | ------------: | -------- |
| d             |           100 | 01100100 |
| o             |           111 | 01101111 |
| g             |           103 | 01100111 |

## Encryption Process

XOR each plaintext binary value with the matching key binary value.

c XOR d:

01100011
01100100
00000111

a XOR o:

01100001
01101111
00001110

t XOR g:

01110100
01100111
00010011

Encrypted binary:

00000111 00001110 00010011

Encrypted hexadecimal:

07 0E 13

## Decryption Process

To decrypt, XOR the encrypted binary with the same key.

00000111 XOR 01100100 = 01100011 = c

00001110 XOR 01101111 = 01100001 = a

00010011 XOR 01100111 = 01110100 = t

Decrypted message:

cat

This proves the decryption works because the decrypted plaintext matches the original message.

## Different Length Plaintext and Key

If the plaintext and key are different lengths, the key can be repeated until it matches the length of the plaintext. For example, if the message is “computer” and the key is “dog,” the key becomes “dogdogd.” Then each character of the message is XORed with the matching character of the repeated key.

## Challenges Encountered

One challenge was making sure each character was converted correctly into 8-bit ASCII binary. Another challenge was carefully applying XOR because one small mistake in a bit can change the final encrypted hexadecimal value. I solved this by checking each line one step at a time.

## Flowchart

Start
↓
Choose plaintext message
↓
Choose key with same length
↓
Convert plaintext to ASCII binary
↓
Convert key to ASCII binary
↓
Apply XOR to each pair of binary values
↓
Convert encrypted binary to hexadecimal
↓
XOR encrypted binary with key
↓
Confirm decrypted message matches original
↓
End
