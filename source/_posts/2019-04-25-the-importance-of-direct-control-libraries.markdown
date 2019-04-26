---
layout: post
title: "The Importance of Direct Control Libraries For Inner Sourcing Model"
date: 2019-04-25 19:46:35 -0700
comments: true
categories: 
---

Before diving into why this type of libraries is important for inner sourcing model
let me explain what I mean by these terms.

You've probably heard about the Inversion of Control principle and about IOC containers.
This concept is particularly popular in Java world. You may have heard of Guice and Spring.
They are inversion of control containers.
The idea of inversion of control is that instead of calling functions with arguments we call function that does some general purpose
thing and then we customize its behavior by passing it lambdas and other functions.
These functions that we pass should satisfy certain requirement in order to be executed
in the function. They need to have certain signature and preserve certain invariants.

Sometimes this idea is extended on the whole application when the application uses
a library that contains your main function and you only need to provide classes and
lambdas that will be executed by the framework. You need to follow certain rules
to execute these values.
