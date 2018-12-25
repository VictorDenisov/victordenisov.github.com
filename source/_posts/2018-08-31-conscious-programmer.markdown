---
layout: post
title: "Conscious Programmer"
date: 2018-08-31 01:32:37 -0700
comments: true
categories: 
---

Authors of some blog posts on the Internet deprive software engineering of the
right to be called an engineering discipline. They like to give examples how
accountable and responsible real engineers are and how reckless are software
engineers. As a person who spent 7 years in university learning different areas
of math in order to become a software engineer I find those statements
preposterous and insulting. At the same time I'm have to admit that a lot of
practices that I see in the industrial software engineering give some ground to
those statements. I arrive to a conclusion that even if software is an
engineering discipline not everyone practices it as such.

Let's discuss what issues are there in software engineering that allow people
to make those statements.

// Lack of adherence to design principles
After ten years in the industry I'm disappointed by how things are done in
software engineering. The experience that you gain while working as a software
engineer doesn't elevate you. You keep debugging things again and again without
any chance not to encounter those issues later. Somebody will make the same
mistake that somebody did before and you will need to troubleshoot this issue
over your weekend. There is no tradition to follow the principles of design
that would allow developers to avoid those mistakes. Andrew Hunt and David
Thomas discuss these principles in their book Pragmatic Programmer. I've never
seen those principles applied consciously in practice. Notorious user's
convenience that drives design processes instead of mathematical purity. For
some reason developers assume that their software will be used by brainless
monkeys.

// problem with databases
Fashion and market opportunity drive design decisions. The industry is not set
up to make conscious decisions. We have many products with similar
characteristics and community keeps creating new versions of the same thing
introducing the same problems. Why do we have five relational databases?! Every
new database claims to be better than all previous ones. After building the new
database its developers start creating connectors to old databases in order to
be part of the community and not to be rejected. From outside it may look like
conspiracy theory. Programmers create jobs for themselves.

// solution
In these cases I like to say that there is no need to look for conspiracy where
you can explain everything with negligence. Instead of creating five databases
we need to create medium sized components that allow use to quickly construct
any of those databases. Every creator of a new database who realized another
use case where a database can be useful should go back and break existing
databases into smaller pieces with his new understanding of the domain and
build his new database with some more approaches. I have to acknowledge that
this process maybe longer than write something from scratch. No venture
capitalist will fund years of refactoring of old databases in order to build
another one in one day.

// the nature of software engineering

Unlike what software engineering does to programs, science refines and expands
its theories. Many people tend to compare software engineering to manufacturing
process. I find this comparison inaccurate. Software engineering is more like
design process.

In manufacturing you need to create blueprints specific to the manufacturing
line. Similar parts need to be redesigned for new manufacturing lines.

Software engineering has this unique ability to reuse blueprints without
implementing them in the physical world.

Every blueprint is already product. In software engineering the product is very
malleable. As such in software engineering it doesn't make sense to create
another blueprint if you already have one. You need to go back split initial
blueprint for designing two parts and ship your new product as two blueprints -
the part that is common with the previous product and the new blueprint that
defines your unique feature of your product.

Instead of building several databases or even building one totally configurable
database we need to decompose our database into smaller blocks that allow us to
build any of them at our discretion any time and the way that is the most
convenient for us. That can be embedded in any system.


Scientific approach to developing libraries.

How does science work? We add layers of knowledge on top of existing layer
we restructure existing knowledge, but we never recreate existing concepts.
Nobody has several implementations of Newtonian physics where gravity works
slightly different in different implementations. Software engineering
should employ similar approach.

Reusable implementations of existing algorithms that can be assembled into
anything we want like Lego bricks.


Software systems are the most complicated systems we've ever dealt with in the
history of mankind.

// Languages

Programming languages are excellent abstractions, but we need to go higher.

// Suggestion

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

