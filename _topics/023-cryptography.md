---
layout: page
title: Cryptography
---

One of the most important applications of number theory to the real world is in its connections to **cryptography**, the study of methods of transmitting information in ways that keep it from being understood by outside parties.

We will start with some ancient methods of cryptography coming from the ancient Romans, and culminate with a description of modern RSA cryptography.


## Caesar Cypher

One of the earliest known examples of a cryptographic system is known as **Caesar cipher**, a name which comes from the fact that the famous Roman emperor was known to use it himself in some communications.

In Caesar cipher, the letters of the alphabet A, B, C, ..., and Z are replaced with the integers $$00, 01, 02,\dots 25.$$
Then each number $$X$$ is replaced by the number $$X+3$$ modulo $$26$$, and finally converted back into letters.

**Example:**

The message *attack now* becomes the sequence of numbers 

$$00\ 19\ 19\ 00\ 02\ 10\ 13\ 14\ 22$$

Now we add three to each number modulo $$26$$, getting

$$03\ 22\ 22\ 03\ 05\ 13\ 16\ 17\ 25$$

Converting this back into letters, we have the encoded message

*dwwdfn qrz*.

The Caesar cypheer is one of the simplest examples of a cipher, and as such is one of the most insecure.
You could hand this cipher to a group of students and by the end of the day, plausibly see them crack it completely.

## Polyalphabetic ciphers

One of the main problems with the previous method is that the same letter ends up with the same symbol.
This makes determining which symbols are which letters far easier.
Thus it is desireble to obtain a more sophisticated method which creates a **polyalphabetic cipher**, one where the the same letter may be represented by multiple different symbols.

### Vigenere's cipher

One of the most famous original versions of this is called  **Vigenere's cipher**, whose encryption is based on a code word that both parties decide on together.
This word could be something like *ghost*.

Then to encrypt the emessage *attack now*, we convert to numbers like for the Caesar cipher but then repeat the phrase ghost, also converted to numbers underneath, repeated as many times as necessary.


$$\begin{align}
  00\ 19\ 19\ 00\ 02\ 10\ 13\ 14\ 22\\
  06\ 07\ 14\ 18\ 19\ 06\ 07\ 14\ 18
\end{align}$$

Now to get the encrypted phrase, simply adds the two columns together modulo $$26$$, obtaining 

$$06\ 00\ 07\ 18\ 21\ 16\ 20\ 02\ 14$$

This gives us the encoded message *gahsvq uco*, which can be quickly decoded by any party that knows the special key word *ghost*.
Already this is an improvement over the previous, since the same letter may be represented by different symbols, etc.
However, it is still insecure in the sense that if one can figure out just the length of the keyword, methods such as frequency analysis may be used to break the code entirely.


### Hill's cipher

Another example of a polyalphabetic cipher is called **Hill's cipher**, and is based on performing $$2\times 2$$ linear transformations.

Start with four numbers $$a,b,c,d$$ satisfying the property that $$ad-bc$$ is relatively prime to $$26$$.
The phrase to be encoded is broken up into $$2\times 2$$ blocks of numbers, with potentially an extra *X* at the end to make the number of letters even.
For each pair of numbers $$P$$ and $$Q$$, we perform the linear transformation

$$P\mapsto aP + bQ\mod 26,\ \ \ Q\mapsto cP + dQ\mod 26.$$

The sequence of numbers $$(a,b,c,d)$$ works as a key allowing the user to either encode or decode a message.

**Example:** Take $$(a,b,c,d) = (2,3,5,8).$$  Then the phrase *hide* becomes the pair of numbers $$07\ 08$$ and $$03\ 04$$

The pair $$07\ 08$$ is encoded as

$$07\mapsto 2\cdot 07 + 3\cdot 08 \equiv 14\mod 26$$

$$08\mapsto 5\cdot 07 + 8\cdot 08 \equiv 03\mod 26$$

Likewise, the pair $$03\ 04$$, is encoded as

$$02\mapsto 2\cdot 02 + 3\cdot 03 \equiv 13\mod 26$$

$$03\mapsto 5\cdot 02 + 8\cdot 03 \equiv 08\mod 26$$

Thus the new numbers become $$14\ 03\ 13\ 08$$, giving us the phrase *odni*.


## Modern cryptography

Starting in the 1970's, cryptographic algorithms relying on exponentials and congruence modulo integers became popular.
Unlike previous systems, these systems relied on *two* keys, rather than just one: one key to encrypt and another to decrypt.

The sender chooses a prime $$p$$ and a number $$k$$ with $$\gcd(p-1,k)=1$$.
The pair $$(p,k)$$ amounts to their **encryption key**, which they use to encode their message, and which may be used to decode it later.

A phrase is converted into numbers, then chopped up into blocks of four-digit numbers, which are transformed as

$$P\mapsto P^k\mod p$$

Then to decode the message, the receiving party needs an integer $$j$$ with $$jk\equiv 1\mod p-1$$, so that if they raise the transformed value $$P^k$$ to the power of $$j$$, they get by Fermat's Little Theorem

$$(P^k)^j = P^{jk}\equiv P\mod p,$$

thereby recovering the original message.

**Example:** Choose an encryption key like $$p = 2609$$ and $$k=19$$.

Then to send a secret messagee like *the crow caws at midnight*, we convert to numbers as usual, but mashed together as one long single number

$$190704021714220200221800191208031308060719$$

This number is then broken up into chunks of four numbers, possibly adding on some *X*'s (ie. $$23$$'s) at the end to make it a multiple of $$4$$.

$$1907\ 0402\ 1714\ 2202\ 0022\ 1800\ 1912\ 0803\ 1308\ 0607\ 1923$$

Now each of the four-digit numbers is transformed by

$$P\mapsto P^{19}\mod 2609$$, giving us

$$0966\ 0094\ 2499\ 1460\ 0930\ 1800\ 0146\ 0135\ 1258\ 0518\ 0761$$

which becomes the number

$$09660094249914600930180001460135125805180761$$

Note that this no longer has an alphabetical interpretation in its encoded form.

To decode this, we can take the encryption key and use the Euclidean algorithm to determine

$$1 = 4\cdot 2608 + (-549)\cdot 19.$$

This maas that $$-549\equiv 2059$$ is a multiplicative inverse of $$19$$ modulo $$2608$$.  So by raising each four digit group to the poweer of $$2608$$ and modding by $$2609$$, we go back to the original message.


### Public key cryptography

The method just described still suffers from a fatal flaw of all the other methods -- one has to come up with some external way to safely deliver the decryption key to another party.

To fix this and truly get to the form of cryptography used in the modern day, the idea of **public key cryptography** was invented.
In public key methods, the reciever openly broadcasts a **public key**, the information necessary to encrypt data and then send it to the reciever.
The reciever keeps a second half of the key, the **private key**, which allows them to decrypt the data.
Typically the private key can theoretically be derived from the public key, but in practice the computation required to derive it would take many, many years even for  computer.  Thus the content of the message is protected.


### RSA cryptography

The most popular form of public key cryptography used today is RSA cryptography.
In RSA, the reciever openly broadcasts a public key consisting of a number $$n$$ which is the product of two very large primes, as well as a number $$k$$ with $$1 < k < \phi(n)$$ and with $$k$$ relatively prime to $$\phi(n)$$.

The user encodes the message as described above, breaking a number into 4-digit blocks, and transforming each block by

$$P\mapsto P^k\mod n.$$

Then the reciever, who knows both the primes $$p, q$$ satisfying $$pq=n$$ thus can easily calculate $$\phi(n) = (p-1)(q-1)$$ and use the Euclidean algorithm to find an integer $$j$$ with $$jk\equiv 1\mod \phi(n)$$.
Thus they can decode the message as described above.

Anyone observing from the sidelines, can see the encoded message as well as $$k$$ and $$n$$.
However, factoring a large number $$n$$ into a product of primes is hard -- very very hard.
It will take them many years to determine the factorization and thereby also be able to decode the message.

