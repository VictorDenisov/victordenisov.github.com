---
layout: post
title: "Conscious Programmer"
date: 2018-08-31 01:32:37 -0700
comments: true
categories: 
---

Authors of some blog posts on the Internet deprive software engineering of the
right to be called an engineering discipline. They like to give examples of how
accountable and responsible real engineers are and how reckless are software
engineers. As a person who spent 7 years in university learning different areas
of math in order to become a software engineer I find those statements
preposterous and insulting. At the same time I'm have to admit that a lot of
practices that I see in the industrial software engineering give some ground to
those statements. I arrive to a conclusion that even if software is an
engineering discipline not everyone practices it as such.

// Lack of adherence to design principles
After ten years in the industry I'm disappointed by how things are usually
done. The experience that you gain doesn't elevate you. You keep running into
the same issues that you need to troubleshoot over your weekend. There is no
tradition to follow the principles of design that would allow developers to
avoid those mistakes. Andrew Hunt and David Thomas discuss these principles in
their book Pragmatic Programmer. I've never seen those principles applied
consciously in practice. Notorious user's convenience drives design processes
instead of mathematical purity. For some reason developers assume that their
software will be used by brainless monkeys.

Software developers can decide to use a library without fully understanding the
characteristics of the library. It's unheard of in any other engineering
discipline to use a material with unknown parameters.

Software is one of the most complex systems we've ever dealt with in the
history of mankind. The horizon of available programs and libraries constantly
expands. In these circumstances programmers are forced to act with some
uncertainty. Writing a new piece of software is like sending a moon probe.
Every time we argue whether the Moon is solid.

Fashion and market opportunity drive design decisions. The industry is not set
up to make conscious decisions. We have many products with similar
characteristics. Software community keeps creating new versions of the same
thing introducing the same problems.

Why do we have five different databases?! Every new database claims to be
better than all previous ones. After building the new database its developers
create connectors to old databases. They want to be a part of the community.
Otherwise the inertia will spew them. From outside it may look like conspiracy
theory. Programmers create jobs for themselves. Companies waste their resources
picking among all possible options or maintaining all of them.

// solution

In these cases I like to say that there is no need to look for conspiracy where
you can explain everything with negligence. Instead of creating five databases
or even creating one highly configurable database we need to create medium
sized components that allow us to quickly construct any of those databases. /*
long sentence */ Every creator of a new database who realized another use case
where the database can be useful should go back and break existing databases
into smaller pieces with his new understanding of the domain and build his new
database with some more approaches. I have to acknowledge that this process may
take longer than writing from scratch. And no venture capitalist will fund
years of refactoring of old databases in order to build another one in one day.
But it saves time to the end user.

I see open source as the solution to this issue. Only users of the software
themselves can build the right tool. They won't care about marketing their
tool. They will use this tool themselves. They know what they need. It makes
the process of software development very much like science. Unlike what
software engineering does to programs, science refines and expands its
theories. Many people tend to compare software engineering to manufacturing
process. I find this comparison inaccurate. Software engineering is more like
design process.

In manufacturing you need to create blueprints specific to the manufacturing
line. Similar parts need to be redesigned for new manufacturing lines. Software
engineering has this unique ability to reuse blueprints without implementing
them in the physical world.

In software engineering every blueprint is already a product. This product is
very malleable. As such, it doesn't make sense to create another blueprint if
you already have one. You need to go back split the initial blueprint, pick the
part that you need, complement with missing part, and  ship your new product.
You product will consist of two blueprints - the part that is common with the
previous product and the new blueprint that defines your unique feature of your
product.

In science we add layers of knowledge on top of existing layers. We restructure
existing knowledge, but we never recreate existing concepts. Nobody has several
implementations of Newtonian physics where gravity works slightly different in
different implementations. Software engineering should employ similar approach.
Reusable implementations of existing algorithms that can be assembled into
anything we want like Lego bricks.

Modern programming languages are a break through in this area. But we still
have a huge gap between the abstractions that modern languages provide and
libraries. Languages give us too small abstractions. Libraries give us too big
abstractions. The great number of different languages only inhibits the
formation of this middle layer.

// Suggestion

So, let's start picking our tools and libraries carefully without creating
redundancy. Let's tear existing tools apart in order to create new tools from
those parts. Those smaller parts in their turn can serve somebody else in their
projects.

And we need to have one language that is truly universal. We don't have such a
language yet. This language should produce truly composable primitives. So far
it looks like Haskell is the one. Though the language research is still in
progress.

I'm happy to report that in recent years great software with focused purpose
started emerging. I would like to endorse suckless tools. They provide truly
reusable pieces of software. Xmonad and similar minimalistic window managers
perfectly complement suckless tools. These programs allow you to build desktop
environment that can evolve with your understanding of efficient workspace.

Unix philosophy is another great example of how composable programs can be built.
