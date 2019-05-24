---
layout: default
---

# What is it?

**SAEAES** is a family of authenticated encryption algorithm submitted to 
[NIST Lightweight Cryptography Project](https://csrc.nist.gov/projects/lightweight-cryptography). 

## Timeline
* May 08, 2018: The SAEB paper is published
* February 25, 2019: Submission Deadline
* April 18, 2019: Announcement of the Round 1 Candidates
* May YY, 2019: The web page is open


# Design

SAEAES is based on **SAEB** which is a mode of operation that extends
a block cipher into authenticated encryption that provides both
confidentiality and integrity of message.  SAEAES is an instantiation
of **SAEB** with the standard block cipher **AES**. The name SAEAES is
named by replacing the **B** for block cipher with **AES**.

## AES

AES is the NIST standard block cipher ([FIPS
197](https://csrc.nist.gov/publications/detail/fips/197/final)). Because
of the intensive use of AES, more and more platforms have hardware
accelerators for AES. Major CPUs such as x86 and ARM have special
instructions for accelerating AES. Besides, many microcontrollers,
used in embedded systems like automotive ECUs and smartcards, has AES
co-processors. SAEAES enjoys the benefit of these hardware
accelerators as an algorithm based on AES.

## SAEB

SAEB is a lightweight block cipher-based authenticated encryption
designed specifically to provide good performances in platforms with
limited computational resources. SAEB can be realized with smaller
memory foot print in software implementations and with smaller circuit
area in hardware implementations.

There are five features that makes SAEB suitable for lightweight
implementations.

1. Minimum internal state size: SAEB uses no extra state i.e., memory except the ones used within a block cipher.
1. Inverse free: aaa.
1. the procedures consisting of XOR operations only, 
1. online, and 
1. efficient static AD handling. 


SAEB follows the sponge-based design methodology except that
it bases on a block cipher but a permutation. SAEB can be thought as a
cascaded n-bit block cipher. The state size of SAEB is n bits, and a
block cipher decryption is not used. Therefore, the properties 1 and 2
are satisfied. The data blocks (either for AD, nonce, plaintext, or
ciphertext) are absorbed into the internal state between the block
cipher encryptions using XOR. Hence, the properties 3 and 4 are
satisfied. Since AD is absorbed earlier than the nonce, the internal
state after absorbing AD is the same for the static AD, and thus the
property 5 is satisfied.


# Contact

xxx

# Reference

1. Y. Naito, M. Matsui, T. Sugawara, and D. Suzuki, “SAEB: A Lightweight Blockcipher-Based AEAD Mode of Operation,” IACR Trans. Cryptographic Hardware and Embedded Systems 2018(2): 192-217 (2018), [PDF](https://tches.iacr.org/index.php/TCHES/article/view/885).
1. NIST Lightweight Cryptography Project [link](https://csrc.nist.gov/projects/lightweight-cryptography)


