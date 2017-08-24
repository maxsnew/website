    Title: Sums are not Coproducts
    Date: 2017-08-24T00:00:00
    Tags: category theory, type theory, curry-howard, by Max New

<!-- In this post I want to share something that tripped me up in my -->
<!-- understanding of the relationship between type theory and category -->
<!-- theory that is glossed over in most introductory discussions. -->
<!-- It's a simple idea but I think it shows that the way category theory -->
<!-- is usually introduced to PL researchers/students is at its very core -->
<!-- misleading. -->

<!-- <\!-- more -\-> -->

The most famous theorem of categorical logic is that simply typed
lambda calculus (product types, unit type and function type with
\\(\beta,\eta \\)) is the internal language of cartesian closed
categories: categories that have finite products and exponentials.
Of course functional programmers know that the only type as cool as
the function is the sum: that's how we get our beloved algebraic data
types and exhaustive pattern matching.

Then that famous theorem can be extended to say that simply typed
lambda calculus with products, unit, functions, sums and the empty
type is the internal language of *bi*cartesian closed categories,
which are usually described as cartesian closed categories that also
have finite coproducts, the dual of the product.
This is all very lovely and a great opportunity to introduce the
beauty of categorical duality, but it's deeply misleading!

You might then go on to say, hey maybe I want to make a first order
language so I can compile it to simple C code, so I don't want any
function types.
What does this language correspond to?
Based on the above, you'd think that a simply typed language with
products, unit, sums and the empty type is the internal language of
bicartesian categories, after all the "closed" part above refers to
the exponentials which are the interpretation of functions.
But you'd be wrong!

It turns out that sums in the usual simple type theory are not *just*
coproducts, they are *distributive* coproducts: coproducts that
distribute over products like in algebra class:
\\[
	A \times (B + C) \cong (A \times B) + (A \times C)
\\]
It turns out that when you have exponentials too, coproducts are
automatically distributive (see a proof [here](???)).


