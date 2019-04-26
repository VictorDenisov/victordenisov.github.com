---
layout: post
title: "Coproduct in Golang"
date: 2019-03-24 19:46:06 -0700
comments: true
categories: 
---

Coproduct in Golang according to 1. should be implemented as standard visitor pattern from OOP:

In this post I would like to research the performance implications of using golang
as described here: 

The implementation suggested in 1 shows heavy use of interfaces.
I would like to understand how much of performance loss it produces.
I decided to implement a simple coproduct type and run it through pprof and
through escape analysis. Let's see what it can do.

Let's start by implementing the value type:

```
type Node interface {
	Name() String
}

Let's implement a visitor.

First in order to define visitor for 

Links:

1. https://making.pusher.com/alternatives-to-sum-types-in-go/
1. https://segment.com/blog/allocation-efficiency-in-high-performance-go-services/
