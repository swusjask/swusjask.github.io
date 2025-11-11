---
layout: single
title: 'CIMPA Research School on Arithmetic in Action: A Deep Dive into Lattice-Based Cryptography'
date: 2025-09-22
math: true
categories:
- Cryptography
tags:
- research school
- lattice based cryptography
---

![CIMPA Research School](/assets/img/cimpa/cimpa-photo.jpg)
This July 2025, I had the incredible opportunity to participate in the CIMPA Research School on "Arithmetic in Action: Number Theory and its Applications to Cryptography and Coding Theory" held at Universitas Gadjah Mada in Yogyakarta, Indonesia. As a cryptography enthusiast, this experience was amazing and really opened my mind to the deep mathematical foundations underlying modern cryptographic systems.


## CIMPA Research School

CIMPA (Centre International de Mathématiques Pures et Appliquées) regularly organizes mathematics research schools in developing countries, and it was a remarkable coincidence that this program was held in Indonesia with topics directly related to the mathematical background needed for cryptography. The program ran from July 14-25, 2025, bringing together students and researchers to explore the connections between pure mathematics and practical applications.

The research school featured six comprehensive courses:

- **Algebraic Number Theory** (Fabien Pazuki and Valerio Talamanca)
- **Elliptic Curves** (Francesco Campagna and Richard Griffon)
- **Lattices** (Michel Waldschmidt and Adeline Roux-Langlois)
- **Modular Forms** (Samuele Anni and Pee Chon Toh)
- **Cryptography** (Any Muanalifah and Indah Emilia Wijayanti)
- **Coding Theory** (Anna Maria Iezzi and Elisa Lorenzo Garcia)

What made this program perfect for me was its advanced master's level content. Surprisingly, I could follow along really well with most of the courses. Having encountered many of these concepts before (except modular forms), I found myself more in a reviewing mode, validating and deepening my understanding of familiar territory. This validation was incredibly valuable for building confidence in my mathematical foundation.

## A New Perspective on Lattice-Based Cryptography

The lattice course, taught by Professor Adeline Roux-Langlois, deserves special recognition for completely transforming my understanding of lattice-based cryptography. I want to give my big appreciation to Prof. Roux-Langlois for her exceptionally clear explanations of the fundamental concepts.

Before this course, my relationship with lattices was purely adversarial. As a CTF cryptography player, lattices meant one thing: breaking cryptosystems by applying LLL reduction wherever possible. My mindset was entirely focused on the attack side, viewing lattices as tools for cryptanalysis.

The course fundamentally shifted my perspective from "how to break crypto with lattices" to "how lattices can be the foundation of secure cryptosystems." The key insight was understanding the complete theoretical framework:

**Worst-case lattice problems** (like SVP, CVP) → **Average-case problems** (SIS, LWE) → **Practical cryptographic schemes**

This reduction chain is what makes lattice-based cryptography powerful. The security of practical schemes is based on average-case instances of SIS (Short Integer Solution) or LWE (Learning With Errors), which have been proven to be at least as hard as worst-case approximation problems on lattices. These worst-case problems are believed to be computationally intractable. The reduction works as follows: worst-case lattice problems reduce to average-case LWE/SIS instances, which in turn reduce to the security of cryptographic schemes. This means that anyone who can break a lattice-based cryptosystem can also solve average-case LWE/SIS problems, and consequently can solve worst-case lattice problems that have resisted decades of research.

One particularly helpful part was learning about how complexity landscape of lattice problems. Coming from CTF, I would always use LLL without truly understanding when the problems were hard to solve. The course explained how different approximation factors change how hard the problems are, and why certain parameter choices make problems take exponential time to solve while others can be solved in polynomial time.

This theoretical foundation is especially relevant given the current NIST Post-Quantum Cryptography standardization. Many of the selected algorithms, including Kyber (key encapsulation) and Dilithium (digital signatures), are built on these lattice-based foundations using Module-LWE and SIS-based constructions respectively.

## Exercise Solutions

Throughout the course, I worked through challenging exercises that helped me to bridge theoretical concepts. Here I share my worked solution specifically for lattice based cryptography on Lattice course. For detailed solution you can read below

<object data="/assets/pdf/solution.pdf" type="application/pdf" width="100%" height="300px">
  <p>PDF preview not available. <a href="/assets/pdf/solution.pdf">Download the PDF</a></p>
</object>

*Having trouble viewing? [Download the PDF directly](/assets/pdf/solution.pdf)*

---

That's my experience at the CIMPA research school! If you have any questions about lattice-based cryptography or want to discuss any of the solutions, feel free to reach out. Always happy to chat about crypto and math stuff.

Thanks for reading! 🙂
