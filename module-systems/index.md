---
layout: page
title: Module Systems
---

# Module Systems


## Courses

- [_Parametricity and Modular Reasoning_](https://wiki.mpi-sws.org/star/paramore)  
  by [Derek Dreyer][dreyer]


## Modular Type Classes

[_Modular Type Classes_](http://www.cse.unsw.edu.au/~chak/papers/DHC07.html) - the original paper  
by [Derek Dreyer][dreyer], [Robert Harper][harper], and [Manuel M.T. Chakravarty][chak].

I found the paper kind of tough going but I recall that presentation gives a
really good intuition about it.
<http://www.mpi-sws.org/~dreyer/talks/popl07.ppt>
[View via Google Docs](https://docs.google.com/viewer?url=www.mpi-sws.org/~dreyer/talks/popl07.ppt)

Extract of the SML code from the presentation/paper
<https://github.com/steshaw/playground/blob/master/sml/typeClass.sml>

The authors note that to make these "type classes" convenient in SML,
you'd need to add implicit parameters (ala Scala - this is after
Odersky's "poor man's type classes" but I'm not sure if they were
inspired by it here).

A related paper with Stefan Wehr:
<http://www.cse.unsw.edu.au/~chak/papers/modules-classes.pdf>. Stefan
further developed theses ideas in his [thesis with a Java extension][wehr].

[Scott Kilpatrick][skilpat] (working on "modules" for Haskell — a better package
system AFAIK). This is [Backpack](http://plv.mpi-sws.org/backpack/) for
Haskell/GHC.

Scott's revelation when he finds the "modular type classes" work
<http://skilpat.tumblr.com/post/208298998/max-planck-and-modular-type-classes>

[MixML](http://www.mpi-sws.org/~rossberg/mixml/) — ML module system inspired by
Scala/Odersky. Really like the look of this compared to OO-style mixin
composition in Scala.

My understanding is the ML-style modules (i.e. modules from SML and
OCaml) use a limited form of dependent typing. i.e. they are like
records/structs with type members (in addition to fun/val members). They
are not first-class like they are in Scala but special functions which
operate on modules called functors (not to be confused with
fmap-Functors or Applicative Functors). These module functors are
parameterised modules.

### Related

#### [Bruno C. d. S. Oliveira][oliveira]

[Type classes as objects and implicits](http://ropas.snu.ac.kr/~bruno/papers/TypeClasses.pdf)

Bruno Oliveira went on to write a paper about "implicits" with some
other folks.

<http://ropas.snu.ac.kr/~wclee/papers/pldi12a.pdf>

The idea is to study the "implicits" as a separate language feature that
should be considered by language designers, or in their words "This
calculus isolates and formalizes the key ideas of Scala implicits and
provides a simple model for language designers interested in developing
similar mechanisms for their own languages.".

#### [Odersky][odersky]

Odersky introduced implicit parameters to Scala in version 2.0.
He explained how that gets you to "type classes" at this talk:

<http://lampwww.epfl.ch/~odersky/talks/wg2.8-boston06.pdf>

and again (more formally) in 2010:

<http://ropas.snu.ac.kr/~bruno/papers/TypeClasses.pdf>

#### [George Kuan][kuan]

-   [A True Higher-Order Module System](http://smlnj-gforge.cs.uchicago.edu/scm/viewvc.php/*checkout*/papers/hofsem/dissertation/kuan-dissertation.pdf?root=smlnj),
    George Kuan, Ph.D. Dissertation, University of Chicago, 2010.
-   [LinkedIn profile](http://www.linkedin.com/pub/george-kuan/6/672/324)

### Modular type classes show-stopper?

<http://lists.seas.upenn.edu/pipermail/types-list/2009/001405.html>

<http://permalink.gmane.org/gmane.comp.science.types/4869>

<http://permalink.gmane.org/gmane.comp.science.types/4875> "In contrast,
since the type of x is universally quantified, the canonical instance of
Num a **must** be determined dynamically (i.e. passed in as an
argument)."

### Modular type classes and deriving

- [_Practical Generic Programming with OCaml_](http://research.microsoft.com/en-us/um/people/crusso/ml2007/slides/yallop-ml07.pdf)  
  by Jeremy Yallop, LFCS, University of Edinburgh, ML Workshop 2007.

### Orphan instances

It seems that Haskell's Type Classes **do** find instances by linking
only. i.e. instances are automatically exported/imported from the
defining module (+ any recursively imported modules when importing).

<http://www.haskell.org/haskellwiki/Orphan_instance>

"Partial Revelation feature of Modula-3 which causes similar problems
like Haskell's type class instances" Link to partial Revelation is
broken. This might be a good substitute
<http://www.cs.tut.fi/lintula/manual/modula3/modula-3/html/partial-rev/index.html>

IMO this is much better solved with "normal" scoping rules (including
implicit definitions).

[dreyer]: http://www.mpi-sws.org/~dreyer/
[harper]: https://www.cs.cmu.edu/~rwh/
[chak]: http://justtesting.org/
[wehr]: http://www.stefanwehr.de/
[skilpat]: http://www.mpi-sws.org/~skilpat/
[oliveira]: https://i.cs.hku.hk/~bruno/
[odersky]: https://lampwww.epfl.ch/~odersky/
[kuan]: https://people.cs.uchicago.edu/~gkuan/
