---
title: "Service and Message Definitions in GRPC"
date: "2023-11-27"
categories: 
  - "book-notes"
tags: 
  - "grpc"
---

The slow crawl through _GRPC: Up and Running_ continues. [You can purchase it here](https://www.amazon.com/gRPC-Running-Building-Applications-Kubernetes/dp/1492058335).

I honestly haven’t made a ton of progress because I’ve read and re-read the same few pages while doing the coding examples. However, I did get through most of chapter 2 which gives a very preliminary introduction to using Protobuf and gRPC. I have one more thing to do to finish it off which is running building and running the app (all done through the coding examples that they give, none done from my own creativity).

One of the things that has thrown me for a loop while reading this is the order that they present information. They went into some Java stuff to build out the client and then they went into setting up Gradle. As a person that barely knows Gradle (like just enough to get by on my day to day work), it would have been more helpful if they presented setting up the Gradle project before showing the code examples. Perhaps it’s just me.

So, what have I learned? A lot. Here are some GRPC specific things. There was a ton that I thought was pretty “common sense” and carried over from my general programming knowledge that I didn’t note here.

- Service definitions is one of the first things you do and that is set up in the proto files. Once you define the definition and compile the proto files, it generates an interface where then you can define the implementation of each method.
- A service is a collection of methods that are exposed (and can be executed by the client).
- Alongside service definitions, you can also define message types. A message is the data structure that is exchanged between client and service. A message type contains fields (similar to an object) and each field is numbered so that the field can be uniquely identified.
- We can only have 1 input parameter per method and can only return one value (I knew this already but worth knowing that the same holds true in the GRPC world). If we need to pass multiple values, we need to define a message type and group all the values.
- You can import from another proto file if you need to use message types defined elsewhere.
- You can manually compile the proto file(s) using the protocol buffer compiler or leverage something like Gradle that has a Protobuf plugin that can do it when you run the build step.

This is as far as I’ve really digested. I’ll cover the rest of chapter 2 once I’ve really digested it and executed the code. However, I’ve been trying to move slower through this book so I can really absorb what it has to offer.

The side challenge of all this is deciding on the the tools I want to invest in. At my job, the tools to use are given. There are certain tools supported by the company that will facilitate getting the job done. However, for my own personal stuff, I always struggle between going to what is familiar vs something different. Going with the familiar means purchasing the same tools that I use at work. That works fine but if the whole point is to learn new things, that's not fulfilling the mission. Going with something completely different means that I'm expanding my horizons and pushing my comfort zone out more.
