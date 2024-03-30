---
title: "Starting to learn gRPC"
date: "2023-11-21"
categories: 
  - "book-notes"
tags: 
  - "grpc"
---

I started reading gRPC Up and Running. [Purchase it here](https://www.amazon.com/gRPC-Running-Building-Applications-Kubernetes/dp/1492058335).

I’ve finished the first two chapters of this book and my first impression is that it started out slow but quickly picked up pace and jumped right into the details. I still have a long ways to go before finishing the book but so far, I think I like it. I’ve dissected a small part of the first chapter and compiled some of my notes.

The g in “gRPC” stands for something different in every release. I didn’t know this. I just assumed that it stood for Google. Very clever.

The general process for developing a gRPC application is as follows:

- Develop a service interface in a proto file
- Generate server side code (server skeleton)
- Generate client side code (client stub)

The client can invoke methods in your service interface. gRPC framework deals with all the complexities that includes handling strict service contracts, serialization of data, network communications, authentication, access control, observability, etc.

gRPC uses protocol buffers as the IDL (Protobuf). Protocol buffers are language agnostic and platform neutral. It is the mechanism used for serializing structured data.

gRPC is the child of many iterations of protocols that came before it. Some of those predecessors include:

- Conventional RPC
- SOAP
- REST

It also discusses the downsides of REST.

- Inefficient text-based message protocol
- Lacks strongly typed interfaces between apps
- Hard to enforce

More to come later but this is as much as I've gotten so far. I plan on writing and running their code examples for some hands on experience.
