---
layout: post
title: "Clojure day"
description: "A new language"
category: daily
tags: [programming, anime]
---
{% include JB/setup %}

Today feels like I did very little, which is kind of disappointing.  I lost my streak in HabitRPG for the first time since I started using it, and it's only the first week!  I need to do better.

I got caught up on some anime I've been watching: Sakura Trick, Sekai Seifuku Zvezda, and Tonari-kun.  While doing so, I got to eat delicious macarons that Alisa baked last night, which were amazingly delicious.  Other lazy day things I did was look into music stuff.  I had an extended conversation with mezmor about music that we've made as well as good music that we'd like to make, and I'm really excited about moving in with him so that we can work together on projects as well in the future.  I'm kind of lazy about putting together music.  When I checked on (my soundcloud)[https://soundcloud.com/corbins/], it said it had been almost a year since I last put up any music.  (And that's including my private secret unfinished tracks.)  I should start working on that this semester.

I mentioned yesterday that I was going to start learning Clojure for my CS242 programming assignment, and I spent a lot of today digging through that.  For some reason I had very little motivation to get started in reading tutorials, mostly because I didn't even know where to start in programming in Clojure.  Eventually I did get stuff set up, but it was already way past dinner at this point.  It interfaces really well with Emacs (obviously) and I really like that I can just compile and set the REPL namespace to my program really easily using cider.

As far as learning the language itself, I had to dig around the concept of "How do I represent a node in a graph with multiple properties?"  In an OOP language, this is a simple answer, just make a class.  The problem is Clojure is not an OOP language, so I needed to rid myself of the notion of just developing a class.  Eventually I came across the notion of protocols and records, which help solve this problem, as well as allow me to extend the library in the future, which the MP will make me do anyways.  I really like how the code wolooks, so as a sample, here's the definition I made for the GraphProtocol I'm using:

'''Clojure
;;I based my implementation off of the library Loom

;;Protocol to represent directed graph;
(defprotocol GraphProtocol
  (cities [graph] "Returns the list of cities in the graph.")
  (routes [graph] "Returns the list of routes in the graph.")
  (add-cities [graph cities] "Adds cities to the graph.")
  (add-routes [graph routes] "Adds routes to the graph.")
  (remove-cities [graph cities] "Removes cities from the graph.")
  (remove-routes [graph routes] "Removes routes from the graph.")
  (clear-graph [g] "Removes all cities and routes from the graph."))
  '''

See?  Super clean and super awesome.  For anyone interested in learning more about Clojure, I'll share a few articles that I found helpful:

(Basic Clojure Tutorial)[http://moxleystratton.com/clojure/clojure-tutorial-for-the-non-lisp-programmer]
(Protocols vs Multimethods)[http://adambard.com/blog/structured-clojure-protocols-and-multimethods/]
(Clojure Graph Library: Loom)[https://github.com/aysylu/loom]
(Clojure in Emacs)[http://www.braveclojure.com/using-emacs-with-clojure/]
