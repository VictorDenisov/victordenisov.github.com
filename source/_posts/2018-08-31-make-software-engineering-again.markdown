---
layout: post
title: "Make Software Engineering Again"
date: 2018-08-31 01:32:37 -0700
comments: true
categories: 
---

Authors of some blog posts on the Internet berate software engineering for not
being an engineering discipline. They like to give examples how accountable and
responsible real engineers are and how reckless are software engineers. As a
person who spent 7 years in university learning different areas of math in
order to become a software engineer I find those statements preposterous and
insulting. At the same time I'm willing to admit that a lot of practices that I
see in the industrial software engineering give some ground to those
statements. I come to a conclusion that even if software is an engineering
discipline not everyone practices it as such.

Let's discuss what issues are there in software engineering that allow those
people to make those statements.

After 10 years in the industry I'm disappointed. You don't gain experience. You
keep debugging things again and again with no chance not to encounter this
issue later. // Scientific programming. Science doesn't rewrite theories.

Unlike software engineering in its current form science refines and expands
theories. Many people tend to compare software engineering and manufacturing process.
This analogy can't be further from the reality. Software engineering is more
like design process. You don't same things again and again. If you are building
it again then it's wrong or everything that was built before you is wrong.
Moreover, if you need build a similar thing again in the future then it means
you never learn. Software engineering has this unique ability to reuse
components. In the real world you can reuse only blueprints and using those
blueprints you can build something new. If you alter this blueprint and create
another blue print for another product then nobody cares. Because first blue
print was from the series of original parts, your new blue print is for you new
product. In software engineering it doesn't make sense. Every blue print is
product. In software engineering the product is very malleable. As such in
software engineering it doesn't make sense to create another blueprint if you
already have one. You need to go back split initial blueprint for designing two
parts and ship your new product as two blueprints - the part that is common
with the previous product and the new blueprint that defines your unique
feature of your product.

Software systems are the most complicated systems we've ever dealt with in the
history of mankind.

The industry is not set up to make conscious decisions. We have many products with
similar characteristics and community keeps creating new versions of the same
thing introducing the same problems. Why do we have 10 relational databases.
Every new database claims to be better than previous databases. Then this new
database starts creating connectors for new databases in order to be part of
the community and not to be rejected. From outside it may look like conspiracy
theory. Programmers create jobs for themselves. In these cases I like to say
that there is no need to look for conspiracy where you can explain everything
with the lack of care. Instead of creating ten databases we need to create medium
sized components that allow use to construct any of those databases in an instant.
Every creator of a new database who realized another use case where a database
can be useful should go back and break existing databases into smaller pieces with his
new understanding of the domain and build his new database with some more approaches.
I have to acknowledge that this process maybe longer than write something from
scratch. No venture capitalist will fund years of refactoring of old databases
in order to build another one in one day.

- Fashion
- Market opportunity

Let's start picking our tools and libraries carefully without creating
redundancy. Let's tear existing tools apart in order to create new tools from those parts.
Those smaller parts in their turn can serve somebody else in their projects.

Software developers can decide to use a library without fully understanding
the implications of using this library. It's unheard of in any other engineering
discipline to use a material with unknown parameters. However because of
complexity of software and constant expansion of the horizon of available
programs and libraries programmers are always forced to act in the environment
of some uncertainty. Every time writing a new piece of software are like
sending a moon probe and arguing whether the Moon is solid.

Scientific approach to developing libraries.

How does science work? We add layers of knowledge on top of existing layer
we restructure existing knowledge, but we never recreate existing concepts.
Nobody has several implementations of Newtonian physics where gravity works
slightly different in different implementations. Software engineering
should employ similar approach.

Instead of building several databases or even building one totally configurable
database we need to decompose our database into smaller blocks that allow us to
build any of them at our discretion any time and the way that is the most
convenient for us. That can be embedded in any system.

Reusable implementations of existing algorithms that can be assembled into
anything we want like Lego bricks.

And we need to have one language that is truly universal. We don't have such a
language yet.
This language should produce truly composable primitives.
So far it looks like Haskell is the one.
Though I believe it's still in research stage.

Open source is a solution for good tools.

Examples of properly designed tools. The truly versatile tools - the tools that
cover not just several known usecases, but can be used the ways their authors
never anticipated.

Suckless tools - cut the complexity.

Companies explode like supernovae spewing matter for new planets and stars.


Awk and sed.

What is wrong with software engineering

