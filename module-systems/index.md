---
layout: page
title: Module Systems
---

# Module Systems


## Courses

- [Parametricity and Modular Reasoning](https://wiki.mpi-sws.org/star/paramore), [Derek Dreyer](http://www.mpi-sws.org/~dreyer/)


## Modular Type Classes

[Modular Type
Classes](http://www.cse.unsw.edu.au/~chak/papers/DHC07.html) - the
original paper.

These kinds of papers can be tough going but I recall that presentation
gives you a really good intuition about it.
<http://www.mpi-sws.org/~dreyer/talks/popl07.ppt>
[QuickView](https://docs.google.com/viewer?a=v&q=cache:cx96awCp_lIJ:www.mpi-sws.org/~dreyer/talks/popl07.ppt+&hl=en&pid=bl&srcid=ADGEESg5e53hOkNZbmS0DeLJXGi53_bh1sP-L5LwI3TDc6E2EzXcwJ3DV-mbgFsi3TLY7sS2jgXJvaCl9nmma4pLJSBTnjPZEBiQIixaNwGxCOpzf_hWWbaMETVEVywbvWBw-ar62CLR&sig=AHIEtbQBIMONy2dxxecTju1aCnWiTcdn0A)

Extract of the SML code from the presentation/paper
<https://github.com/steshaw/playground/blob/master/sml/typeClass.sml>

The authors note that to make these "type classes" convenient in SML,
you'd need to add implicit parameters (ala Scala - this is after
Odersky's "poor man's type classes" but I'm not sure if they were
inspired by it here).

A related paper with Stefan Wehr:
<http://www.cse.unsw.edu.au/~chak/papers/modules-classes.pdf>. Stefan
further developed theses ideas in his thesis <http://www.stefanwehr.de/>
with a Java extension.

[Derek Dreyer](http://www.mpi-sws.org/~dreyer/) — Uber researcher on
module systems.

Scott Kilpatrick (working on "modules" for Haskell - a better package
system AFAIK). <http://www.mpi-sws.org/~skilpat/>. This is
[Backpack](http://plv.mpi-sws.org/backpack/) for Haskell/GHC.

Scott's revelation when he finds the "modular type classes" work
<http://skilpat.tumblr.com/post/208298998/max-planck-and-modular-type-classes>

MixML - ML module system inspired by Scala/Odersky
<http://www.mpi-sws.org/~rossberg/mixml/> Really like the look of this
compared to OO-style mixin composition in Scala.

My understanding is the ML-style modules (i.e. modules from SML and
OCaml) use a limited form of dependent typing. i.e. they are like
records/structs with type members (in addition to fun/val members). They
are not first-class like they are in Scala but special functions which
operate on modules called functors (not to be confused with
fmap-Functors or Applicative Functors). These module functors are
parameterised modules.

### Related

#### Bruno Oliveira

[Type Classes as Objects and
Implicits](http://ropas.snu.ac.kr/~bruno/papers/TypeClasses.pdf) (email
to self 03-May-2012)

(Email to Mark Perry 31-Oct-2013)

Bruno Oliveira went on to write a paper about "implicits" with some
other folks.

<http://ropas.snu.ac.kr/~wclee/papers/pldi12a.pdf>

The idea is to study the "implicits" as a separate language feature that
should be considered by language designers, or in their words "This
calculus isolates and formalizes the key ideas of Scala implicits and
provides a simple model for language designers interested in developing
similar mechanisms for their own languages.".

#### Odersky

(Email to Mark Perty 31-Oct-2013)

Odersky introduced implicit parameters to Scala in version 2.0. BTW,
this was when I started taking Scala more seriously (but not just
because of the implicit parameters!).

He explained how that gets you to "type classes" at this talk:

<http://lampwww.epfl.ch/~odersky/talks/wg2.8-boston06.pdf>

and again (more formally) in 2010:

<http://ropas.snu.ac.kr/~bruno/papers/TypeClasses.pdf>

#### George Kuan

-   [A True Higher-Order Module
    System](http://smlnj-gforge.cs.uchicago.edu/scm/viewvc.php/*checkout*/papers/hofsem/dissertation/kuan-dissertation.pdf?root=smlnj),
    George Kuan, Ph.D. Dissertation, University of Chicago, 2010.
-   [homepage](http://www.cs.hmc.edu/~gkuan/)
-   [LinkedIn
    profile](http://www.linkedin.com/pub/george-kuan/6/672/324)

### Modular type classes show-stopper?

(email to self, 08-Jul-2012)

<http://lists.seas.upenn.edu/pipermail/types-list/2009/001405.html>

<http://permalink.gmane.org/gmane.comp.science.types/4869>

<http://permalink.gmane.org/gmane.comp.science.types/4875> "In contrast,
since the type of x is universally quantified, the canonical instance of
Num a **must** be determined dynamically (i.e. passed in as an
argument)."

### Modular type classes and deriving

[Practical Generic Programming with
OCaml](http://research.microsoft.com/en-us/um/people/crusso/ml2007/slides/yallop-ml07.pdf),
Jeremy Yallop, LFCS, University of Edinburgh, ML Workshop 2007.

### Orphan instances

(email to self, 11-May-2012)

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

---
(Adapted from [email to coq-study mailing list, 05-Mar-2013](http://lists.bfpg.org/mailman/private/coq-study/2013-March/000129.html))
