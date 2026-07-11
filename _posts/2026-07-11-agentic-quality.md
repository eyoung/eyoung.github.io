---
layout: post
title:  "Quality in an agentic world"
categories: software, craftsmanship, agentic, AI, LLM
excerpt_separator: <!--more-->
---

What does quality mean in this new agentic world we are on in. This is a question that has literally kept me up at night. 
How do we know the output of agents works? How do we know we implemented all of the product criteria? How do we know the code is up to our quality standards if we didn't write it or fully understand it? Does our old measure of quality even matter?

<!--more-->

These are questions I don't have answers to yet but like everyone else, I'm starting the journey to figure it out.

## Product Critera

For product criteria, I have found asking agents to build a small product spec is very helpful. In my experience this has been a very effective way to help manage context and keep the agent on track with what it's trying to build. For best results I recommend focusing on small focused specs rather than trying to build a spec for the entire application.

As a bonus, the agents are also really good at comparing the implementation to the spec to make sure all of the acceptance criteria got implemented

## Code Quality

Even in this agentic world, I am convinced good tests are our best tool for building quality software. Good tests mean we have a good metric that the behavior works. And testable code tends to be well architected code. Getting the agent to build consitently good tests can be a struggle. The agent wants to move fast and solve the problem. That's what it is trained to do. Getting it to slow down and let a solution emerge brings a lot of friction to the process. For this I've started reworking my testing skills to make it pair with me on every test so I can give feedback on whether the test is a good test at all, and testing the right boundary. 

My workflow here has gradually shifted from `Implement this feature with TDD (Test Driven Development)` to `Work with me to identify a first good test` and we work together to make sure we are testing the right thing and then I can leave it alone for a red-green-blue iteration and verify the output is in line with my own quality standards. 

Maybe as I refine my own skills and rules files I can let the coding agents do more of the TDD loop on its own but for no, I find myself much less frustrated leveraging the agent as something to pair with on test than as a fully autonomous unit. 

## Architecture

I am also convinced clean architecture is still just as important as it has ever been as well. For a while I did question, why do I need my code to be easy to change if a coding agent and spec can just rebuild the whole thing in an hour. For the time being, yes maybe they can reimplement the spec, but at what cost? In this case literal money cost. Good code is easy to change and extend. In the past this cost was paid in developer time and frustration. Now? We're paying in AI tokens for real money. All of these abstraction layers we've build are just as important. Spaghetti code application with raw database calls everywhere will cost significantly more tokens to migrate to a new storage backend, whether it's moving persistence to the cloud or changing to some newer more shiny database engine. Something utilizing Hexagonal Architecure or any other form of clean arcitecture will be able to do that migration with just a new `Repository` implementation at a fraction of the cost.

## The workflow

So what does generating code for me look right now? Well this could change tomorrow with how fast everything is moving these days. But as of this blog...

1. Invoke my agent skill to define a `spec.md` for my feature.
2. Review the spec and make sure the behaviors are properly defined.
3. Invoke TDD skill and identify a good first test
4. Iterate through TDD red-gree-blue phases for each behavior
5. Review the code myself
6. Submit my code for code review

So far this is working well for me and feels like a true accelerator in my day to day work. I'm excited to see how this evolves over the next few years.