---
layout: post
title:      "DISCLAIMER: Written by MICHAEL MCTIGHE"
date:       2020-07-03 15:13:43 +0000
permalink:  disclaimer_written_by_michael_mctighe
---

# What on Earth is Big O Notation.


Before we get into the mix here I want to go over a few things. Like what we will learn in this blog.
# Things we will NOT accomplish
Kind of weird yes I know, but I think it is important.
1.  We will NOT know the language (or O(n), O(1), etc) to judge and algorithm.
2.  We WIll NOT become masters of this topic in one blog.
3.  and finally this is NOT the end all be all guide to Big O Notation read and absorb as much as you can.
# Great Mike so what is it then?
This blog is here to just make you a bit more comfortable with the idea of Big O Notation.This will also help with demonstrating the process and demystifying some big math words. I have never been a Huge math guy so I have to simplify it so it make sense to me and hopefully you too!
# I have got a one way ticket to Boundtown!
Like many things in life like Big O Notation are a part of something bigger than itself. Now, to the weird header. Some people refer to Big O as *Asymptotic Bounding* and when someone told me that for the first time my head exploded. After picking up the pieces of my brain I started to breakdown what it had ment. If you are a Math person you know where this train is headed and I am sure growing up I had asked you for homework. Sorry. But for the Birds of a feather that I fly together with I had no clue what it ment. So what is an asymptote. Well its the behavior of a function as it approchies an untouchable bound. Again when I herd that my head exploded but this time smaller and into less pieces. I still needed to break down what a bound is. From what I have found a bound is just a very large value. Hey Mike, really sorry to do this but where do this fit in to the *bigger picture* that you were talking about. Good question totally fictional reader. Big O Notation only represents the Upper bound. everything from the y axis to the give value or as we know the bound. 
# Why do I have to care about this? 
When I was first learning programing and you write your first program and it works you mind is blown. You are basically a greek god weilding the power of electricity, comunicating with a being(a computer) that does not speak your language. But just like picking up a new language in the natural world it takes time and enegery to learn. It goes the same way with the code you write everyday. Aware of it or not the actions you preform in the IDE have a cost. Instead of time and enegrey it takes to learn spanish. We measure the cost of an algorithm by its time and space complexity. Only if there was some sort of weird math that we may or may not have read in the paragraph above.
# Back to Boundtown
So now that we have a better picture of why Big O is used and why we should care about it we can go one level deeper. Your probly thinking "finally we get to see those weird symbols". The symbols refering to the measurements we take from a given algorithm to determine it cost respectively time and space. But no, there is one more thing I want to talk about before we get to the fun stuff. The relation to the bound itself. We know what bound we are in and we know why we should care but that still does not aswer the question. A bound is a value from what we have learned eariler. I am going to put the formula here:
```
T(n) = O(f(n)) ← T(n) <= c*f(n) ∀ n >= nₒ   
```
![](http://static.boredpanda.com/blog/wp-content/uploads/2015/04/shocked-animal-funny-fb.jpg)
I know. 
# Symbol guide 
I am going to take out all of the jargon and attempted to bring understanding.
```
a = b
```
Simple enough the variable a that is equal to the variable b.
```
what does this weird arrow mean (←)
```
All that the arrow is saying that variable a is equal to the variable b if something is true. Thats it, Its nothing more than a conditional.
Lets see what we are checking. all we want to check is if a = b. Then the next chunk says.
```
c <= e*f
```
This next chunk states that the variable c is less than or equal to whatever the variable e times the variable f is.
Now we are getting back to the land of the unknown the letter A is upside down.
 `∀`
Thats great and all Mike but what does it mean. In math it represents predicate logic and stands for: for all, for any, for each or for every. In this case we mean for all. So now that we know what that weird A means we can tackle the next chunk.
```
g >= gₒ
```
It looks great! the variable g is less than or equal to the variable g with an odd 0 hanging off of it. Wait a second we have not gone over that yet! So what does it mean? It is a variable with a subset and subset represents what we are looking at in a sequence. What this is trying to say in confusing math is that *g is greater than or equal to the variable g at this spot*.
Here is my makeshift equation, I will show the fourmula and then write it out in regular english.
```
a = b ← c <= e*f ∀ g >= gₒ
```
Ok it looks a bit more confusing now but with the breakdown it should make more sense. So we have a variable a is equal to variable b, if the variable c is less than or equal to the variable e times the variable f, for all variable g is greater than or equal to the variable g at the given position of 0.  
# No way
Yep, this euqation is just used to determine how close an input is to the bound. The next blog I write will have our measurements ( O(1), O(n), etc) I hope this blog cleared some stuff of for you and be on the look out for the next one
Thanks!
