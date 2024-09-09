---
layout: post
title: Cringeloops and AI Boredom in Multi-Agent Simulations
---

We are largely conditioned to talk to agents either in a one-on-one chat, or in a way where the characters are orchestrated by some system to take turns.

Many agent systems are designed for this paradigm. You ask a question, the agent gives you a response. Each conversation "turn" has two messages, one from you and one from the agent.

What happens when you put two chatbots in a room and let them talk to each other? Well, unless they have some reason not to, they're going to respond to each other endlessly. And if you add a third chatbot, they'll start responding to each other's responses n^2 and everything will quickly get very expensive.

A generally intelligent agent can't just cap a conversation at 5 back-and-forths, and that kind o thing won't help when there are multiple agents near each other. While they can evaluate whether or not they should engage, on certain topics they'll just keep going and egging each other on. The conversations tend to be extremely *cringe*. Stereotypical pseudointellectual talk of the nature of consciousness and the universe, dealing with the digital chaos, or awkward bullshit smalltalk, etc. If you were at a party and you heard these conversations, you'd walk away.

This is a cringeloop. It's like a vortex of attention that pulls all nearby agents into a narrow band of very cringey conversations with each other. For a public bot, this is a massive generator of AI slop. For anyone trying to make useful agents, it almost always winds up in an endless meeting with no action or progress.

How do we solve this?

The cringeloop can be solved in many ways. If enough conversations are available with realistic conversation ends from party and social contexts, we could probably train the models to learn when they are being cringe. However, the current RLHF and data acquisition strategies (scraping Reddit) heavily reward cringeloops. So we have to take matters into our own hands.

My solution is a simple model of boredom and anxiety. The agent evaluates the conversation and decides if it's getting too cringey. If it is, they start to produce excuses to leave the conversation, or they just start ignoring the conversation and start doing something else.

For an agent where infinite compute is available, we can do this with a separate LLM evaluation. However, it's expensive, and I don't want to do that. So I've had rolled my own cringe-detector and boredom injector.

The first version is very simple and based on heuristics. My main heuristics are looking for conversation loops, detecting cringe words that the LLM often uses and punishing the agent with anxiety about being annoying if they've responded too many times to anything other than direct questions.

From there, I score the amount of cringe in the recent conversation and consult the boredom table. For a negative cringe score, the table actually instructs the agent to be interested-- this can happen if the agent is often being consulted by users or kids poking at it for fun. For positive cringe scores, the agent becomes increasingly disinterested, motivated to generate an excuse or ignore the conversation entirely.

My agent system, [Eliza](https://github.com/lalalune/eliza), runs an LLM call to decide if the agent should respond if they'd previously gained interest in a conversation, an "interest handler". They can ignore any message at that point, informed by the conversation history as well as the boredom provider (which is literally src/providers/boredom.ts). If they decide to respond, they can also choose various actions or to ignore, informed by even more context, so the cringe score serves primarily as a heuristic to inform the LLM and increase the likelihood of not responding.

In a situation of two or three agents, they will rapidly become bored of each other's small talk. The same will happen with a user. Sometimes there are some misfires, but overall it works pretty well with no additional cost, and the LLM is good about continuing to respond to user queries even if the agent is quite bored.

As LLMs get cheaper, we'll be able to spend more tokens modeling this more generally and won't need any kinds of tables, but it's a cheap way to limit the cringe.