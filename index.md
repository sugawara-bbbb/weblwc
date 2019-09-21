---
layout: default
---

# SAEAES

**SAEAES** is a family of authenticated encryption algorithm developed
by Mitsubishi Electric Corporation and The University of
Electro-Communications, and submitted to [Lightweight Cryptography
Project](https://csrc.nist.gov/projects/lightweight-cryptography) by
National Institute of Standards and Technology (NIST).

## Timeline
* May 08, 2018: The SAEB paper is published
* February 25, 2019: Submission Deadline
* April 18, 2019: Announcement of the Round 1 Candidates
* May 25, 2019: The web page is open
* Jun 13, 2019: A minor bug fix in the SAEB paper (typos of Fig. 2): [the updated paper](https://eprint.iacr.org/2019/700)
* Aug 30, 2019: SAEAES is selected as a [Round 2 Candidate](https://csrc.nist.gov/projects/lightweight-cryptography/round-2-candidates).

# Design

**SAEAES** is based on
[SAEB](https://tches.iacr.org/index.php/TCHES/article/view/885), which
is a mode of operation that extends a block cipher into authenticated
encryption that provides both confidentiality and integrity of a
message. SAEAES is an instantiation of SAEB with the standard block
cipher
[AES]((https://csrc.nist.gov/publications/detail/fips/197/final)). The
name SAEAES is named by replacing the B for block cipher with AES.

## AES

AES is the NIST standard block cipher. Because
of the intensive use of AES, more and more platforms have hardware
accelerators for AES. Major CPUs such as x86 and ARM have special
instructions for accelerating AES. Besides, many microcontrollers,
used in embedded systems like automotive ECUs and smartcards, have AES
co-processors. SAEAES enjoys the benefit of these hardware
accelerators as an algorithm based on AES.

## SAEB

SAEB is a lightweight block cipher-based authenticated encryption
explicitly designed to provide excellent performances in platforms with
limited computational resources. SAEB can be realized with smaller
memory footprint in software implementations and with smaller circuit
area in hardware implementations.

![SAEB](/assets/img/all.png)

SAEB follows the sponge-based design methodology but uses a block
cipher instead of a permutation. Five features that make
SAEB suitable for lightweight implementations.

1. Minimum internal state size: no additional state is needed on top of
the ones within the block cipher.
1. Inverse free: block cipher decryption is not used.
1. XOR only: the additional operation other than block cipher encryption is XOR only.
1. Online: an incoming message is scanned only once (rate 1).
1. Efficient static AD handling: the result of the hash can be reused for another message with the same AD.


# Reference

1. Y. Naito, M. Matsui, T. Sugawara, and D. Suzuki, “SAEB: A Lightweight Blockcipher-Based AEAD Mode of Operation,” IACR Trans. Cryptographic Hardware and Embedded Systems 2018(2): 192-217 (2018), [PDF](https://tches.iacr.org/index.php/TCHES/article/view/885).
1. Y. Naito, M. Matsui, T. Sugawara, and D. Suzuki, “SAEB: A Lightweight Blockcipher-Based AEAD Mode of Operation,” Cryptology ePrint Archive, Report 2019/700, 2019 [PDF](https://eprint.iacr.org/2019/700).
1. NIST Lightweight Cryptography Project [link](https://csrc.nist.gov/projects/lightweight-cryptography)


