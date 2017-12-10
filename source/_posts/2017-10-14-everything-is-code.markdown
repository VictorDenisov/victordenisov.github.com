---
layout: post
title: "Everything Is Code"
date: 2017-10-14 22:14:57 -0700
comments: true
categories: 
---

I started my long path into the world of computing in norton commander. Then I
worked in windows 3.11 and windows 95 all windows through windows 2003, windows
xp. In parallel I was introduced to linux. Initially the only interface I saw
in Linux was pico commander. Then all the associates of xwindow system showed
up - gnome, kde, xfce.

The evolution of interfaces that I learned was from command line to graphical
interface. The introduction of graphical interface seemed to be a progress.
The introduction of touch screen interfaces that came with the advent of iphone
era produced even more confusion. Around that time I graduated from university
and started working in enterprise as a java programmer.

During my 5 years at the university I participated in ICPC. ICPC is an
international competition in programming. You have three people behind one
computer and 8-12 programming problems to solve. First two years we were
programming in Pascal. Third year we programmed in C++ and then moved to Java
and eclipse as an IDE. Java seemed like a progress. Intelligent autocompletion
in Eclipse completely blew my mind. Most of the time we weren't typing - we
were tapping ctrl-space and the IDE seemed to have been writing code for us.
Every winter and summer we used to go to programming camps in Petrozavodsk. To
one of those camps a team from Poland was invited. They were very strong and
they were programming C++ in ... Vim. This discovery completely threw me off.
It was completely unclear to me why they would use Vim. Vim seemed to be
something ancient, completely unfit for our twenty first century. I never
bothered to spend too much time researching this phenomenon, but it definitely
struck me, and I had remembered it.

So, when I went to enterprise I was completely confident that I used the most
advanced technologies for programming. After a couple of years in the industry
I got interested in Vim. It was the only editor available over ssh that we used
for programming on remote dev boxes. I had heard the editor was good and I
decided to give it a try. So I had been merely playing with Vim until I
attended a talk by one of our colleagues - Kirill Ishanov. His introduction to
Vim flipped my world. At that time I hadn't realized all ramifications of my
discovery. Now I can tell you what impressed me - Vim was an interpreter of
text editing language. Every keystroke in command mode is an instruction in
this language. If you want you can put those instructions in a register and
execute them in a batch. It's called macros. You can record macros by entering
commands and specifying what register you want to store them in or you can just
copy a sequence of letters into this register. Then the whole program would be
replayed from this register. That was the moment when I became an ideological
proponent of vim. Vim wasn't just an editor. It was an interactive text
processor.

Now, getting back to java programming language. At the time when I was
programming in java I was under impression that all languages should be or are
like java - some variation of c like syntax, imperative in its nature. It
seemed normal to write code in an editor, then it would be compiled and
executed. Another thing was execution. We used Far manager(clone of Norton
Commander) to run our apps. We rarely typed commands in the command line.
Command line seemed like something old fashioned. We didn't see point to use
it. At some point we started using it only because it was the only way to
communicate to a remote computer over ssh. We didn't like it. It seemed like a
limitation of our abilities. I had had this attitude for command line until I
visited the US for the first time. Engineers at the US office were programming
in vim and were using command line like it was their editor for entering small
programs. I was impressed. I started learning how to use command line as
fluently as they did. Though I couldn't realize the implications of this
discovery until I learned the third missing piece - powerful language with
expressiveness of python and strictness of java. Before I found this language
my understanding of command line was that it should have weird syntax. Haskell
completely rocked my world. Its command line allowed me to find out functions'
types which served as a good documentation. Most of the time I could infer what
functions were doing just based on their name and types. Declarative style of
functional programming worked very well with interactive interpreter. Instead
of giving instructions you were describing what you wanted to get.

This was when I realized that this idea should be taken to the extreme -
communication with a computer should happen inside a language interpreter.
Communication with your fellow programmers should be done through code. Code is
the ultimate way to communicate exactly what you want your computer to do.

Every time I hear someone saying that I they've achieved something on their
computer without writing code and that they avoid writing code because writing
code is erroneous it means they just didn't realize that they wrote a line of
code. If you don't program your computer it means instead of putting your
commands for the computer in a batch and executing them, you execute them
yourself without recording what you've done. It's even more error prone. It's
much harder to improve this way because now you need to remember what you've
done last time and you need to be diligent enough to repeat it precisely again.
Why bother remembering if you can just record your commands and work with them
in a text editor? Text and language are the tools of thousands years old. They
are the best so far to communicate information. Visual information, gestures
are the most effective. But if you want to preserve your knowledge for some
extended period of time then text is the most compact way to do so.

If you write code then you record all the steps that you are about to make. You
can analyze what you are about to do. You can version your code in the most
convenient way that is currently known - version control systems. Also compiler
can help you analyze what you do. Even if you use your computer in an
interactive way then using command line allows you to extend your vocabulary of
commands. You can recall previous commands and reuse them even if you never
bothered to add them to you standard library of commands. Computer is a machine
that is built to execute commands.

Writing code is the best way to interact with your computer if not the only one.
