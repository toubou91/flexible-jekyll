---
layout: post
title:  "How to checkout (on a forked repo) a Pull Request coming from the main repo?"
date:   2018-03-04 10:00 +0200
comments: true
tags: [git, pull-request]
img: coderetreat.png
---

### 1. Introduction
November 2017 I facilitated the [Global Day of Coderetreat 2017](https://www.youtube.com/watch?v=Mp34vCVlSVs) in Utrecht, Netherlands. In the past, I have already attended one [coderetreat in Thessaloniki](https://thodorisbais.github.io/the-first-global-day-of-coderetreat-in-thessaloniki/), Greece, but it was quite different to experience it from the facilitator's perspective. As it was my very first time facilitating such an event, I wanted to keep the amount of people really low (20) and also recruited two co-facilitators, Joost and Patrick. Let's see my notes during the day, while observing who teams were working on each different session.

Disclaimers:
- The notes are not opinionated, I just tried describing what I was observing
- The retros are mostly depicting the participants' views

### 2. The Sessions
Before diving into the sessions themselves, we as facilitators had to make a short introduction on what the day was about, but after some time I was asked from a specific participant about the reason of having such a long intro, since all of us knew why we were there.
In such questions you have to explain that not all the participants know what a Code Retreat stands for and what it is about, so, you patiently have to explain and go on with the schedule you have in your mind.

#### 2.1 Free Approach

###### 2.1.1 Short notes
- People started directly with the code
- Only one team first wrote a test and then decided to solve it on paper first
- While moving around to see how the teams are doing, I stopped at one team and asked "how are we doing?", the answer I got from one of the two members of that team was that the solution they decided to follow was not clear from both of the team members

###### 2.2.2 Retro
- There were arguments regarding the best solution
- One person said "I believe y partner would have given a completely different approach if he was the one who wrote the code"

#### 2.2 String Ping-Pong

###### 2.2.1 Short Notes
- A specific team had an argument regarding the solution they should follow; after not being able to solve it verbally one suddenly grabs the keyboard from his partner's hands and starts typing the solution they agreed upon
- Another team gave a try on a programming language that the person who was writing the code didn't know about (Scala); the result was that one was typing and the other was giving instructions regarding the syntax and the aspects of the language
- While doing one of my normal walks around, I stopped again at a team to see how they were doin' and this is the short chat I had with one of its members:

> Participant: We started by writing a failing test. <br/>
  Me: Cool, so, it started well! <br/>
  Participant: Well, not fast, but I think we got the idea

- A person who was talking about the Scrum methodology during the first session, in the middle of the second session asked confirmation for a specific rule of the game. After a while he started arguing again with his partner regarding Scrum; his partner got a bit pissed off, but they managed to continue. The person who argued was the same person who asked me the question in the introduction.
- The Team which decided to go for Scala finally split, because as one of the members mentioned:

> We couldn't even get the very basic setup done, so, we split.

- Again, to another Team, it was like one knew about the problem and the solution upfront, but was kinda pissed off from the fact he had to wait for his partner
- On another Team, discussions were quite calmed.

###### 2.2.2 Retro
- Miscommunication
- Team had to adjust
- Discussion about clients

#### 2.3 No Talking

###### 2.3.1 Short Notes
- Was difficult for them to communicate
- Once a test was green at a Team, one member was really happy that he shouted:

> Yes, it passed!

- After walking around and observing them for 15', I thought to myself:

> Maaaaaan, it's really difficult for them not to talk

- One Team was still talking even when I was in front of them
- Scala guy insists on using Scala, but still, not sure about it
- A guy didn't want to receive help verbally from his partner and told him to stop telling him what they should do next
- Another Team had fun during this session; after some point, just by sign language they could made clear what their partner meant

###### 2.3.3 Retro
- Different approach than the first two sessions
- Clarity was deviated
- Names, language
- No progress, because of the setup of the session

#### 2.4 No Mouse

###### 2.4.1 Short Notes
- They didn't think about pairing with someone who knows git
- People got annoyed from the fact of not being able to use their mouse:

> _How can this be productive?_

- Explanations between the partners, instead of solving the problem
- The participant who talked the most in overall was bossy giving instructions to his partner

> _It's very dirty, but at least it's working_

###### 2.4.2 Retro
- Our goal today is not to solve the problem
- Have a clear path of dealing with a problem; structured in many commits and visible in the commit message log
- Minimize time wasted on trying an approach. Short commits instead of hours spent
- Understand that a big problem can be split in smaller simple ones

### 3. Overall Retro
This is a quote from a participant that made me really happy:
> _Before reaching the venue, I was thinking "yet another working day, but in the end it proved to be a safe environment"_<br/>

Another quote from a different participant:
>  _No colleagues was good_

One that I liked:
> _Willing to experiment_

One that myself always believes is a first priority in our job:
> _Communication is important_

#### 3.1 What did you learn today
In this question I got the following answers

Something I really expected:
- TDD
- Naming conventions
- Communication
- It's difficult to delete your code after each session

#### 3.2 What are the 3 take-aways for you today?
Again, the one below caught my attention:

> _Remote pair programming might work the way TDD is done_

And of course, our job's headache:

> _How difficult it is to cope with tests_

#### General Points from my side
- Most of the participants came prepared, they knew the problem upfront

### References
- [No talking session footage](https://www.youtube.com/watch?v=p-g9QiGtt4s)
- [A review on the event itself from Piet Souris, one of the attendees](https://coderanch.com/t/687011/books/Global-Day-Code-Retreat-Day#3226936)
- [VLOG #7 - GDCR17 & Utrecht JUG Banner!](https://www.youtube.com/watch?v=_S9qe6eT-0M)
- [Meetup event](https://www.meetup.com/Utrecht-Java-User-Group/events/243847568/)


### 4. Closing Notes
I'm pretty sure you made clear how much I enjoyed this event.


What are your thoughts about it? About a Coderetreat you have attended? About the different kind of personalities one might meet in their orking environment? About how much the setup of an environment can help or not in the way people feel about the da to day work?


Let me know in the comments!