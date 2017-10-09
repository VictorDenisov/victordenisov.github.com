---
layout: post
title: "Linux programming #2"
date: 2013-02-16 15:31
comments: true
categories: 
---
This is the synopsis of the second Linux programming lab.

## The assignment for the second lab

The second assignment is to write a program that prints words which are
combinations of all characters of an alphabet. The combinations should have
certain length. For example, if length of the words is 3 and the alphabet is
"abc" then all possible combinations will be

{% codeblock %}
aaa
aab
aac
aba
abb
abc
aca
acb
acc
baa
bab
bac
bba
bbb
bbc
bca
bcb
bcc
caa
cab
cac
cba
cbb
cbc
cca
ccb
ccc
{% endcodeblock %}

## Naive solution

Here is the easiest solution to print a list like this one above:
{% codeblock primitive bruteforce with nested loops lang:c %}
char * alph = "abc";

for (int k1 = 0; k1 < 3; ++k1)
  {
    for (int k2 = 0; k2 < 3; ++k2)
      {
        for (int k3 = 0; k3 < 3; ++k3)
          {
            printf ("%c%c%c\n", alph[k1], alph[k2], alph[k3]);
          }
      }
  }
{% endcodeblock %}

However this solution has a significant limitation. We can't get words of
arbitrary length. Recursive bruteforce can overcome this limitation.

## Recursive bruteforce

{% codeblock recursive bruteforce lang:c %}
void go (int k)
{
  if (k == N) // N - length of the word
    {
      printf ("%s\n", a);
      return;
    }
  for (int i = 0; i < ALPH_LEN; ++i)
    {
      a[k] = alph[i];
      go (k + 1);
    }
}
{% endcodeblock %}

Invocation of go from the main function looks like this:

{% codeblock recursive bruteforce lang:c %}
go (0);
{% endcodeblock %}

The flowchart of the go function is presented below.

{% img /images/brute_force/recursive_brute_force.png %}

Recursive brute force can be regarded as a process of spawning a copy of the
same function and entering it again with storing the current position.

The following flowchart depicts control flow of a program that prints all words
of length 4. Green lines mean forward pass. Blue lines mean backward pass when
the function returns to the place of its invocation. Black lines stand for
inactive paths.

Press right mouse button on the image and choose "View image" to see full size
image.

{% img /images/brute_force/recursive_brute_force_many.png %}
