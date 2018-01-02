---
layout: post
title:  "Database indexing"
---

Started reading Martin Kleppmann's "Designing Data-Intensive Applications"

On Chapter 3 at the moment, which is about [Storage and Retrieval].  I had saved this Stackoverflow [link](https://stackoverflow.com/questions/1108/how-does-database-indexing-work) from a while ago as well about DB indexing.

So I'm going to write briefly about the following

  - High level understanding of Databases and its functions
  - How concepts such as (Data Models) (Query Languages) relate to databases
  - What is indexing & why we need it

### Database and its functions

A database (sometimes abbreviated to DB) simply serves the following 2 functions

1) Stores data when provided
2) Retrieves data when asked

### Concepts related to Databases

'''
**Data Models**

  - A formatted way in which a person gives data to the DB

**Query Languages**

  - A specific mechanism with which a person asks DB for the data
'''

As you can see, the above 2 concepts are from a **HUMAN perspective** of giving & taking from a database

The reason that I emphasize the human perspective is that these concepts that developers are most commonly faced with,
they do not really cross the interface layer beyond to the underlying concepts of how database systems work internally.

These 2 concepts are really for human consumption - to make the job easier for the developer.

But if you want to optimize performance, you must understand some concepts beyond that interface... which brings us to

### Indexing

If we kept our data in a file (the simplest DB),

As more data is stored, finding queried data will become increasingly slow.  We will have to spend O(n) time searching 

since there are no additional sources that can help us.

This is where indexing comes in...

'''
index : additional data structure that is derived from primary data - one that is maintained at some overhead but helps to find what we want quicker
'''

On each write (adding new entries / data), indices are updated to reflect the new entry --- so overhead for write is introduced
But
On each read, indices are really useful data structures that speed up search --- so improved performance

Since EVERY index introduces overhead for writes, yet NOT ALL indices speed up reads, indices are not the default and must be chosen by the developer


