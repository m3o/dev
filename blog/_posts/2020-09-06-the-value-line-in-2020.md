---
layout:	post
title:	"The value line in 2020: Dev vs Ops"
date:	2020-09-06 10:00:00
---
<br>
<i>Hat tip to my friend James Watters ([@wattersjames](https://twitter.com/wattersjames)) for teaching me about the value line.</i><br><br>
What is the value line? The value line is how you distinguish what's core to your business vs what you can and should outsource. In today's world 
we outsource a lot of things as non-core concerns but somehow continue to blur the line when it comes to Dev and Ops.

I'm here to talk to you about the value line in 2020.

## What's my priority?

The real question you have to start with is, what's my priority? What problem am I solving? Who's my user or customer? 
When you start with these questions then you begin to uncover where the focus really needs to lie. So let's begin with 
a thought experiment.

Alice is setting up a new business. For this example let's say its a Neobank focused on Millenials...

She's identified a real problem, as a millenial herself she understands the pains of managing money in 2020, trying 
to keep track of spending and what's worse, dealing with her bank over the phone or going to a branch when there's a 
problem. Banking just wasn't built for her. She's got a great idea, what if a bank was built just for her.

Alice sets out to solve the problem with an MVP. Her and one other engineer (Joe) figure out how much they need to build to make 
something like this work. They'll need a mobile app, some sort of prepaid card and a way to manage all this on the backend.

Alice knows how to build html5 apps and Joe is a pretty good full stack dev using ruby on rails plus they've seen that 
Stripe is a card issuer so they can potentially tap into that real quick. Alice and Joe decide to use Heroku 
for hosting a rails app with a mysql backend and try get something off the ground using Phonegap. 

Its a convoluted example but here Alice identified the problem was one she felt herself and needed to prototype for quickly. 
Offloading much of the initial tech requirements to a fully managed PaaS, a card issuer with an API and html to app converter.

At every stage of your business you need to identify, what's the problem I'm solving and what tradeoffs am I making to solve that problem 
vs finding a perfectly scalable solution for the future. Basically, what's the value I'm creating and how much operational 
overhead do I need to incur.

Let's take it a step further.

## Initial Traction

Alice and Joe put out the MVP and start getting traction. They're onboarding friends and posting on social media to get some of 
the initial users. The traction is good and they're starting to grow past a couple hundred users with line of sight to a thousand 
in a few weeks. They're already feeling the pains of heroku but decide to double down, phonegap performance is also poor so they're 
trying to find a solution.

Alice decides they should scale the dynos on heroku, pay for more mysql storage and contract a developer for the app side. If the 
app is slow the user experience is terrible and that's what matters. Paying for stuff is one thing, but waiting 2-3 seconds for 
screens to load is terrible. She pays someone part time to start hacking on something for Android since most the users 
are Android users.

Heroku has done its part, it seems costly compared to other solutions, but they don't need to manage anything which means more 
time to spend growth hacking and one less person to pay on the operations side. Phonegap also let them test out the market 
initially but has outlived it's time, they know now the user experience is what matters.

## The Scale Out and Break Out

Things are blowing up faster than expected. Always a good thing, but now, everything's on fire. We need to figure out how to 
deal with the growth in the user base without having to completely rearchitect the stack. We need to break out the hotspots 
in the code into separate services.

Joe identifies that the API is super slow since its written in Ruby. The monolithic app has gotten them pretty far but there's 
alot baked in which could be separated out to be done in a more appropriate language. In this case, the API needs to be 
something more performant since its handling all the requests. It also just uses a ton of memory.

This is going to be non trivial on Heroku. They don't really support service oriented architecture. Everything is going to 
be a public API call. Talking to the backend is going to get complicated. Joe decides he needs to bite the bullet and 
make it work on Heroku, they're invested in it now and it still means they don't have to deal with Ops. 

Joe's been learning some Go and has seen many of the big tech companies adopt in for backend systems. He decides to write 
the API in Go and use a message queue in Heroku with Redis to publish anything to the existing monolith that needs to 
be processed in the background. Its going to require a bit of change in the Rails app but worth the performance gain.

The Go API uses a 1/10th of the memory of the Ruby app, it actually only takes 1 dyno to serve all their needs. The monolithic 
Ruby app has now been left to deal with background job processing and some of the core functionality that was still 
pretty complex. The first phase of scale out and break out is successful.

## Moving Beyond Heroku

It's all going great, but now we've maxed out the capacity of heroku. Breaking down into more services is useful but we're 
incurring some pretty heavy costs to do it with a full blown PaaS. If we evaluate our costs in relation to our customer base
then we're actually losing money rather than making it. We have to find a better alternative. Heroku was built for 
monolithic apps not microservices.

Pragmatism has gotten Alice and Joe this far. They proved out an MVP, got product/market fit and pushed the current 
infrastructure as far as it would go. Now they need to get off Heroku and find a better route forward.

You're thinking I know exactly what you need to do now. A container platform on a major cloud provider. Just spin up 
that managed container orchestrator, learn some yaml, maybe a bit of terraform and off you go. This is where you 
need to start thinking very carefully about the value line. That's right we didn't forget about it.

## The Value Line

Getting to the breaking point in terms of scale both technically and organisationally pushes many companies to bring 
more and more operational burden in house. It is only natural to weigh up the cost of a managed service vs 
our current needs and assume that self managed is the most appropriate choice for the future. 

The customisation, the cost reduction on the managed service itself, all the possibilities. All without thinking about what the 
operational cost and maintenance burden is. I'm here to tell you, this, is a pivotal moment in your company's lifetime. 

Deciding where the value line is for your company now will determine where you spend the majority of your time and money 
moving forward. Self managed is a sunk cost, a pit that becomes incredibly hard to climb back out of. As much as you may 
believe you can transition off the in-house approach, we rarely see it happen.

It is true that when you reach the breaking point of scale you need to start deviating from what worked before. What worked for 
1, won't work for 100, won't work for 1000. But it does not mean you need to take on the entire operational burden of the 
platform owners of today.

## The Backend for Your Frontend

M3O was born with an understanding of this exact pain. At the breaking point of scale every team and organisation has to make a 
choice, either move to a self managed platform to do microservices or incur the costs of solutions that were not built for 
purpose. We felt this pain, so we decided to build a solution.

M3O is a cloud native development platform for Micro services. We focus on providing a fully managed platform for building 
microservices in Go using the open source framework [Micro](https://github.com/micro/micro). The goal is to enable 
large scale developer productivity on the backend while letting the folks like Netlify focus on the frontend.

We think this solution works and why we coined the term, "Netlify for your frontend, Micro for the backend".

Large scale software development is hard. The cloud hasn't made it any easier. In fact we feel like over the past 5 years 
if nothing else it's just gotten harder with all these tools promoted by the [CNCF](https://www.cncf.io/). We think 
things have to change. With millions now expecting online services to scale from day 1, we as software developers need help.

The backend for your frontend. Let us manage the platform, help your write microservices, be super productive. Let 
Netlify deal with the frontend, and talk to us through a single consolidated API. That's right, no need to wrangle 
those microservices yourself into a cohesive API, we do it for you. 

When you're thinking about the value line for your business. When deciding whether the future of your company is developing 
software or managing the operations of it. Choose development every day of the week by letting us deal with the operations.

If you're interested to learn more check out [m3o.com](https://m3o.com) or join us at #m3o-platform on [slack.m3o.com](https://slack.m3o.com).
