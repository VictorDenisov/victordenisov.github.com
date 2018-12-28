---
layout: post
title: ""Terminology Is a Type System""
date: 2018-12-27 16:41:28 -0800
comments: true
categories: 
---

Sometimes, I had troubles understanding my colleagues when we discussed complex
design topics. I couldn't figure out what was the problem. Let alone I couldn't
explain why I didn't understand them. We used to talk about things, but their
meaning was very elusive to me. I couldn't quite grasp the meaning of the words
as they kept changing their shape.

I was saying that we needed to define our terminology. We did it, but next time
somebody used this word I would get lost again. We kept using words in a
somewhat lose way. But I couldn't describe what was wrong with our way. I
couldn't explain how we would need to restrict the usage in order to achieve
shared understanding.

Finally it dawned upon me - terminology is like a type system. We weren't
honoring the type system we created. We kept using strings in place of
integers. We defined an interface, but we forgot to describe the implementation
of this interface for a specific type. As we used this type it wasn't clear to
me how this type behaved when used in place of an interface.

For example we were applying something that could only be applied to tuples to
a single value without defining what it means.

So, basically if you use a notion you first need to define this notion's
properties. And also you need to define its behavior of categories of objects
that you operate with. Describe how your objects interact with other objects.
