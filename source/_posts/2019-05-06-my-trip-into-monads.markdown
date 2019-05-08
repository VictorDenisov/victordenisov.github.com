---
layout: post
title: "My Trip Into Monads"
date: 2019-05-06 19:28:58 -0700
comments: true
categories: 
---
Usually people share their knowledge about monads right after they get to
understand them. I decided to share my experience with monads when a friend of
mine started studying this topic. So here it is - my trip into monads.

In this blog post I'm not going to give you the exhaustive list of all monads,
or explain the theory behind monads. I'm going to share with you the example
that I used to develop intuition about monads.

Let's solve the following problem. We are going to build a library for parsing
different values from a string. For the sake of simplicity we are going to
build two functions. One function parses a number delimited by whitespaces. The
other function will be parsing a string delimited by whitespaces. I'm going to
illustrate what monad is in Go. Our Go will be a slightly special flavor of Go.
It will have genercis. However all the idioms that I demonstrate here are
imported from Haskell.

In this exercise let's imagine that Go is a purely functional language. You
can't use any imperative constructs in our version of Go. With one exception
though. Consecutive assignments are allowed. Those are not imperative
constructs. Also our Go will have two features: generics and tuples. As a
result half of the code here won't compile in Go. This code can be successfully
rewritten in Java and compiled. But I decided to go with the modified Go
instead of Java because of Go's brevity.

Let's declare the type of our first function. The function that parses a string.
This function will be accepting an input string and returning the result and
the remaining string.

{% codeblock parseString lang:go %}
func parseString(s string) (res string, rem string) {
	if len(s) == 0 || s[0] == ' ' {
		return '', s
	} else {
		res, rem = parseString(s[:1])
		return s[0] + res, rem
	}
}
{% endcodeblock %}

ParseInt will look very similar. It can even use parseString except it will need
to convert the result to int.

{% codeblock parseInt lang:go %}
func parseInt(s string) (res int, rem string) {
	resString, rem = parseString(s)
	res, _ = strconf.Atoi(resString) // we are ignoring error for the simplicity of the example
	return res, rem
}
{% endcodeblock %}

Now let's write a function that is supposed to use our two functions. It will
parse an integer and a string from the provided input string. It will also
return the remaining string.

{% codeblock Example lang:go %}
func parse(s string) (a int, b string, rem string) {
	a, rem1 := parseInt(s)
	b, rem2 := parseString(rem1)
	return a, b, rem2
}
{% endcodeblock %}

Now, people who were implementing it for the first time in Haskell noticed that
there is a repetition in this code. We pass the remainder of the previous
parse function and pass it into the next one. They decided to abstract this
repetition into a separate data structure. Let's declare a new structure.

{% codeblock Parser Type lang:go %}
type Parser<V> func (s string) (v V, s string)
{% endcodeblock %}

Now let's change the signature of our parse functions a bit:

{% codeblock New Version of parseString lang:go %}
func parseString() Parser<string> {
	return func (s string) (string, string) {
		if len(s) == 0 || s[0] == ' ' {
			return '', s
		} else {
			res, rem = parseString(s[:1])
			return s[0] + res, rem
		}
	}
}
{% endcodeblock %}

{% codeblock New Version of parseInt lang:go %}
func parseInt() Parser<Int> {
	return func (s string) (int, string) {
		resString, rem = parseString(s)
		res, _ = strconf.Atoi(resString) // we are ignoring error for the simplicity of the example
		return res, rem
	}
}
{% endcodeblock %}

At this point we need to define another interface that our Parser is going to implement:
{% codeblock Monad interface lang:go %}
type Monad<T> interface {
	bind func(f func(v T) Monad<K>) Monad<K>
{% endcodeblock %}

Now let's implement bind function for Parser. Pay attention. This is the most difficult
part of the whole narration.
{% codeblock Parser's Bind lang:go %}

func (p *Parser<T>) bind(f func(v T) Parser<K>) Parser<K> {
	return func (s string) (K, string) {
		value, newS := p(s)
		return f(value)(newS)
	}
}
{% endcodeblock %}

What it does it return a function that is a chain of two functions together. Function p
and function f. Bind method just takes two functions and composes them into a bigger function.

The implementation of our example now turns into the following:

{% codeblock Example With Monads lang:go %}
func parse() Parser<(int, string)> {
	parseInt().bind(func (i int) Parser<(int, string)> {
		parseString().bind( func (s string) Parser<(int, string)>{
		).lift((i, s))
	})
}
{% endcodeblock %}

Here we encounter another method of that every monad should implement - lift. In Haskell this method is called return, but I decided not to use this name in order to avoid
confusion with the built in return. Here is the implementation of lift.

{% codeblock Parser's Lift lang:go %}
func (p *Parser<T>) lift(v T) Parser<T> {
	return func (s string) (T, string) {
		return (v, s)
	}
}
{% endcodeblock %}

Lift just wraps a value into a function.

What we implemented here is called state monad. For me it was the hardest monad
to understand. I hope this blog post helps you in your understanding of monads.
