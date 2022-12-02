# xorpher

Xorpher is a tiny and strong XOR Stream chipher, Unicode compatible, made in JS. Only (1.75 KB)

The main difference from other similar solutions is that for the same plaintext and key it will always generate a different ciphertext every time the encryption function is invoked, so there is no shared pattern between the resulting ciphertexts even from the same plaintext, resulting in "pseudo" one-time pad (OTP) that makes it really reliable against attacks.

### Disclaimer:

Important: It's not intended to be used for high security data. I can't warranty it's totally unbreakable. There are many high security algorithms out there for that porpose. Use this at your own risk.

It was created to serve to a especific porpose: To be tiny, simple, strong, fast, API idepended (works in anything that runs JS) and efficient so that the encrypted data have similar size to the original plaintext (Note that it will be aways 70 characters longer than the plaintext no matter what is the plaintext length. That's for integrity and version control purposes only) thus you can store encrypted data anywhere with a low cost of space and processing power. I recomend usig a key as long as you can, as the length of the key has nothing to do with the ciphertext's final size. A weaky key can be easily brute forced using the algorithm itself. when possible, use a key that has the same length of the message you are encrypting or above if the message is short (less than 16 characters).

### How to use it:

Simply include the file xorpher.js or the function "xorpher" itself in your project, then invoke the encrypt / decrypt functions as follow:

```javascript
let encrypted = xorpher().encrypt("That's my secret message! 😀", "M4aKV#C20%q1Hq&V");
console.log(encrypted);

let decrypted = xorpher().decrypt(encrypted, "M4aKV#C20%q1Hq&V");
console.log(decrypted); //That's my secret message! 😀
```

