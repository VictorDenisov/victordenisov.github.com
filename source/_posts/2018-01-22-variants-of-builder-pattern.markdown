---
layout: post
title: "Classification of Variants of Builder Pattern"
date: 2018-01-22 20:58:57 -0800
comments: true
categories:
---

Intro
-----

Builder pattern seems to be one of the most versatile patterns of all
creational patterns. Its role is usually underestimated and it usually goes
unnoticed among other easier for understanding creational patterns: `Abstract
Factory`, `Singleton`, `Prototype`. Further I suggest to review some of
variations of `Builder` pattern. In certain cases the variations bring
the pattern closer to `Visitor` pattern. In other cases the modifications bring
it closer to `Abstract Factory` pattern. Nevertheless the way it is used stays the same.
All the variants give us fine tuned control over the dependencies and modularity
of the code where the `Builder` pattern is used.

Classic Description
-------------------

`Builder` pattern is widely known from the book by Gang of Four**[1]**

`Builder` pattern separates the process of construction of a complex object from
its representation. So that the outcome of the same process of construction
can be different.

Classic applications of builder pattern is presented on the class diagram
{% img /images/builder/class_diagram.png %}

Sequence diagram 

{% img /images/builder/interaction_diagram.png %}

illustrates the relationship of builder and director with the client. This
variant of `Builder` pattern can be used in a code that is responsible for
building charts of arbitrary format:

```
class PriceData {
    Map<String, Integer> data;
    public void buildChart(ChartBuilder chartBuilder) {
        for (Map.Entry<String, Integer> entry: data.entrySet()) {
            chartBuilder.addKeyValue(
                entry.getKey(), entry.getValue());
        }
    }
}
```

In this case the main application will be a client. The collector of the data
for the diagrams will be a director. The construction of concrete charts(pie
chart, histograms, line chart) will be done by a concrete implementation of
builder - a class implementing ChartBuilder. This usage allows us to abstract
out the process of construction from the concrete implementation of the object
being constructed.

Modifications of The Pattern
----------------------------

In common practice we can encounter modifications of `Builder` pattern that
allow us to manage dependencies inside the project in various ways. The
modifications fall into different categories based on the location of
GetResult method call and on the number of directors.

### Location of GetResult Call

Variations of `Builder` pattern can be classified based on the location of
GetResult call. GetResult method can be called either from the director or
from the client.

#### Invocation From Client
If `GetResult` method is invoked from the client then this variant is for
abstracting out the director from the implementation of resulting object as
it's represented in the classic case.

#### Invocation From Director
In this case the result is required by the director itself, but the director
doesn't know the implementation. If the client doesn't invoke set-methods of
the Builder then this implementation of Builder pattern can be replaced with
`AbstractFactory`. In the case when a part of the director should be configured
before passing it to the director `AbstractFactory` is not suitable because it
focuses on synchronous object construction. In this case `Builder` pattern is the
most suitable option.

```
class ClassProcessor {
    public main() {
        builder = new ExprProcBuilder();
        builder.setClassFields()
        methodProcessor.processMethod(builder);
    }
}
class MethodProcessor {
    public processMethod(ExprProcBuilder builder) {
        builder.addLocalVars();
        builder.buildExprProc()
    }
}
```

### The Number of Directors

Variations of the pattern can also be defined by the number of directors.

#### No Directors

There may be no directors. In this case `Builder` pattern is used as a constructor
with named arguments. Client and director are the same entity.

#### One Director

If there is one director then it leads us to the classical variant of `Builder`
pattern for abstracting out the product construction from its concrete
implementation.

#### Several Directors

There may be more than one director. Everyone in the chain of directors sets
the parameters that it knows about and passes the builder to the next director.
This variant of `Builder` pattern reminds more of `Visitor` pattern. Pattern
`Visitor` is usually used for handling `Composite` pattern. In the case of
`Builder` pattern the visited objects can have arbitrary nature. Here is an illustration
of the case with several directors:

{% img /images/builder/chain_of_invocations.png %}

Features of The Pattern
-----------------------

### Inversion of Dependencies

One of the main reasons to use `Builder` pattern - inversion of dependencies. The
builder is passed to a director during construction, what ensures isolation of the
director from the implementation details of concrete builder.

### Named Arguments of Constructor

Another reason as it's specified in [2] to use `Builder` pattern can be a lot
of arguments of the class being constructed. Let's take a look at a piece of
sample code.

```
new Builder().setA(value1).setB(value2).createProduct()
```

From this code it's clear that `value1` becomes `A` in the new product, and
`value2` becomes `B`. It allows us to change the order of arguments in the
invocation. Named arguments make the code more readable. The invocation of
method `GetResult` is done by the director itself, which is also a client.
`Builder`'s role here is similar to the role of `AbstractFactory` pattern, but
unlike `AbstractFactory` pattern, who's task is to give access to construction
of construction of a group of connected objects, `Builder` is focused on
construction of instances of only one class.

### Decomposition in Time

This pattern also allows us to configure builder as we receive data necessary
for configuring it. So the construction can lapse in time instead of happening
at once as it's done in factories or constructors. `Builder` pattern tracks the
consistency of the object being constructed and if some of the arguments are
missing it can throw exceptions or execute any other action required to inform
about the incomplete state.

### Loosening Coupling

This approach also allows us to loosen coupling between classes. Each class can
set only the arguments this class is aware of and pass the builder further in
the chain of construction. The classes only need to know about the structure of
the builder and don't need to know about each other. They also only work with
the methods they need to know of and don't need to care about the rest of the builder.
This usage of `Builder` pattern makes it very similar to `Visitor` pattern.

Then method `GetResult` can be invoked when the builder is returned back
to the client from the chain of invocations inside directors(in the beginning
of the chain) or by the final director(end of the chain).

### Tolerance for Change of Data Format

If `Builder` pattern is used as in sections `Loosening Coupling` and `Several
Directors` then if we need to collect more data we can use new methods only
where they are required keeping the rest of the chain of directors intact.
Instead of getting data through get methods sometimes it's more flexible to
pass `Builder` pattern.

### Example

Let's illustrate what we described above in the case for several directors.
Method GetResult can be invoked by classA as well as by classC. In both cases
classA and classC can't know anything about each other's dependencies, what
reduces dependencies of each of them, but gives them access to the required
object. In addition to that classC receiving partially configured, can change
only the part he knows about and as a result receiving different objects
depending on the requirements.

The latest approach is particularly convenient, when the client class requires
different instances of a class depending on the data that client class has,
but IOC container restricts access to constructors.

Conclusion
----------

`Builder` pattern is a sufficiently powerful and flexible instrument for
dealing with dependencies inside a project and inversing the dependencies.
Regrettably, the usage of `Builder` pattern requires writing a lot of
boilerplate code. It complicates effective usage of this pattern in modern
programming languages.

As Rob Pike appropriately mentioned in his presentation at OSCON 2010: patterns
- are usually solutions whose implementation is missing from the language. We
can only hope that working with builder pattern in future languages will be as
simple as just writing a constructor.

Appendix A
----------
{% img /images/builder/class_diagram.png %}

Appendix B
----------
{% img /images/builder/interaction_diagram.png %}

Appendix C
----------
{% img /images/builder/chain_of_invocations.png %}

Bibliography
------------

1. Erich Gamma and others. Design Patterns: Elements of Reusable Object-Oriented Software, 395 p.
2. Bloch J. Effective Java. Second edition. Prentice Hall, 2008.
3. More on getters and setters - JavaWorld [Electronic resource]. URL: http://www.javaworld.com/javaworld/jw-01-2004/jw-0102-toolbox.html (date of access: 06.02.2011).
