---
layout: post
title:  "Type-driven development in Haskell, Idris, Rust and Scala: Introduction"
date:   2017-11-05 10:00:00
categories: jekyll blog GitHub-Pages
banner_image: github-pages.jpg
comments: true
author_name: Michael Thomas
---

# Type-driven development in Haskell, Idris, Rust and Scala

## Introduction

Type-driven development can be considered as a style of programming where types guide program development. Generally, this may involve:

* Designing types first and implementing functions later - In this approach, types are designed to model the domain and function type signatures are declared upfront to model the flow of data through the program [1]. With this outline in place, all that is left is the *simple* process of implementing the functions themselves.

* Catching errors at compile time - It is better detect errors at compile-time rather than at run-time. This is safer since it eliminates a whole class of bugs before they can be encountered in a production environment. (Note: tests cannot rule out the possibility of trivial errors whereas a powerful type system can.) In addition, catching errors at compile-time increases development speed since feedback on program correctness is near instantaneous. Contrast this to programming in dynamically-typed programming languages where running the program is required to check that your implementation does not contain any trivial mistakes. The more information that can be encoded into types, the greater the safety guarantees. This highlights the importance of correctly modelling your domain with types.

* Getting help from the compiler while implementing functions - Both Haskell and Idris support the use of typed holes [2]. Typed holes represent a missing part of a program. The compiler is able to provide the types of typed holes, as well as the types of bindings in scope. This knowledge can then be applied to *filling* the typed hole (i.e., implementing the missing part of the program). Haskell and Idris also allow case splitting. For example, say `x` is a `Boolean` type, we could split `x` into its two component parts, `True` and `False`. The combination of typed holes and case splitting is used extensively in Idris to great effect. In Idris, it is even possible sometimes for the compiler to implement an entire function from the function type signature alone!

In this series, I will focus on four statically-typed programming languages; Haskell [3], Idris [4], Rust [5] and Scala [6].

### Haskell

* Pure, functional programming language.
* As the oldest of the four languages, Haskell arguably has the greatest technical debt.
* Small the growing use in production (numerous current job postings in the fintech/cryptocurrencies space).

### Idris

* Pure, functional programming language with dependent types.
* Primarily of research language and not recommended for production.
* Written in Haskell.

### Rust

* Systems programming language backed by Mozilla.
* Provides memory safety without garbage collection using ownership rules.
* Growing use in production [7].
* Most loved programming language according to the 2016 and 2017 Developer Surveys [8].

### Scala

* A multi-paradigm programming language supporting both object-oriented and functional programming styles.
* Runs on the Java Virtual Machine (JVM) (can also be compiled to native binaries [9]).
* Widely used in production, particularly in the area of big data (for example, Spark [10] is written in Scala).


These programming languages all make heavy use of types to ensure program correctness. There are, however, significant differences between the type systems of these languages. These differences arise from different design decisions and language constraints (i.e. Java interoperability in the case of Scala).

#### References
[1] https://underscore.io/blog/posts/2017/04/11/type-tetris.html

[2] https://wiki.haskell.org/GHC/Typed_holes

[3] https://www.haskell.org/

[4] https://www.idris-lang.org/

[5] https://www.rust-lang.org/en-US/

[6] https://www.scala-lang.org/

[7] https://www.rust-lang.org/en-US/friends.html

[8] https://insights.stackoverflow.com/survey/2017#most-loved-dreaded-and-wanted

[9] https://scala-native.readthedocs.io/en/latest/

[10] https://spark.apache.org/
