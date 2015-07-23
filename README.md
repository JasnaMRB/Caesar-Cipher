# Caesar-Cipher
Problem set 6 from MIT 6.00.1 Introduction to Computer Science and Programming using Python

Hail Caesar!

Encryption is the process of obscuring information to make it unreadable without special knowledge. For centuries, people have devised schemes to encrypt messages - some better than others - but the advent of the computer and the Internet revolutionized the field. These days, it's hard not to encounter some sort of encryption, whether you are buying something online or logging into a shared computer system. Encryption lets you share information with other trusted people, without fear of disclosure.

A cipher is an algorithm for performing encryption (and the reverse, decryption). The original information is called plaintext. After it is encrypted, it is called ciphertext. The ciphertext message contains all the information of the plaintext message, but it is not in a format readable by a human or computer without the proper mechanism to decrypt it; it should resemble random gibberish to those for whom it is not intended.

A cipher usually depends on a piece of auxiliary information, called a key. The key is incorporated into the encryption process; the same plaintext encrypted with two different keys should have two different ciphertexts. Without the key, it should be difficult to decrypt the resulting ciphertext into readable plaintext.

This assignment will deal with a well-known (though not very secure) encryption method called the Caesar cipher. In this problem set you will need to devise your own algorithms and will practice using recursion to solve a non-trivial problem.

Caesar Cipher

The basic idea of the Caesar cipher is that you pick an integer for a key, and shift every letter of your message by the key. For example, if your message was "happy" and your key was 3, "h" becomes "k", "a" becomes "d", and so on, because we are shifting every letter three spots to the right. Here is what the whole alphabet looks like shifted three spots to the right:
 
Original:  a b c d e f g h i j k l m n o p q r s t u v w x y z
 3-shift:  d e f g h i j k l m n o p q r s t u v w x y z a b c

Using the above key, we can quickly translate the message "happy" to "kdssb" (note how the 3-shifted alphabet wraps around at the end, so x -> a, y -> b, and z -> c).

Note!! We are using the English alphabet for this problem - that is, the following letters in the following order:

>>> import string
>>> print string.ascii_lowercase
abcdefghijklmnopqrstuvwxyz

In this problem, we will use a variant of the standard Caesar cipher where we will treat upper and lower case letters separately, so upper case letters will always be mapped to upper case letters, and lower case letters will always be mapped to lower case letters. Thus, if "a" maps to "c", "A" will map to "C". Characters such as the space character, commas, periods, exclamation points, etc will not be encrypted by this cipher - basically, all the characters within string.punctuation, plus the space (' ') and all numerical characters (0 - 9).

