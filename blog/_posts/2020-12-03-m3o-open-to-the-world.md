---
layout:	post
title:	"M3O Platform is now open to the world!"
date:	2020-12-03 10:00:00
---
<br>
Today we're unveiling M3O as "open to the world". Head to the [homepage](https://m3o.com) and get started immediately. 
M3O is a fully managed cloud platform for microservices development. It's built based on the 
popular open source project [**Micro**](https://micro.mu) and focuses on developer productivity for backend service development. To read about 
the related Micro 3.0 release head to the [open source blog post](https://micro.mu/blog/2020-11-05-micro-v3-aka-m3o).

Back in May we [announced](/blog/2020/07/30/m3o-a-cloud-native-platform-built-for-developers.html) our goals and efforts towards building a 
shared platform in the cloud for developers to create services without the hassle of managing infrastructure. Since then we've been testing 
this with a small group of paying customers (who we're grateful to) and iterating based on the feedback. Today we're happy to say M3O is 
in a place where we feel excited and confident to offer it everyone.

No more dealing with cloud infrastructure, no more complex dashboards from AWS and others. A purely CLI driven experience and a development model 
baked in for writing microservices. Not only that but the feature set includes the following based on running Micro as a Service.

### Features

Here's a few things to highlight:

- **Microservices development** using gRPC and protobuf code gen
- **Service runtime** and lifecycle management
- **Source to running** builds without need for CI/CD
- **Authentication and authorization** for access control and user management
- **Dynamic configuration** and secrets management
- **PubSub messaging** and event streaming
- **Service discovery** and secure networking
- **Key-value storage** and persistent CRUD
- **Automatic HTTP routing** with path based resolution
- **Identity aware proxy** for remote access and gRPC-web apps
- **Public API gateway** and TLS support by default
- **Public and private repos** support including  github, gitlab and bitbucket


### Tiers

M3O is launching with a simple 3 tier pricing plan; **Dev**, **Platform** and **Cloud**. 

- **Dev** is a free tier for you to get started on. We know the hassles of getting stuff up and running and the costs of Cloud 
(even with credits) so we're making it super simple for developers to get started fast. This is built for small projects and individual devs.

- **Platform** is a paid secure, scalable and supported tier that includes 2x the resource limits of Dev and gives you confidence in a 
platform team managing the infrastructure. When you're done hacking on Dev, switch to the Platform environment and run your 
production services knowing we've got your back.

- **Cloud** is for larger scale teams who want isolated environments in the cloud, whether its self-hosted or fully managed. We'll give 
you the Platform experience but tailored for your needs. While Dev and Platform are multi-tenant shared environments, Cloud is totally 
separate so you know you're the single tenant and owner of those resources.

### Pricing

Unlike cloud compute providers who feel the need to charge per the penny and force to you into using pricing calculators to figure out the 
costs, we're using a simply flat subscription pricing model on a per user basis. Our goal is to focus on abstracting away the details 
of infrastructure including the pricing and let you as a developer just focus on writing code. 

That's why the platform is priced at $35/user/month with unlimited collaborators. Over time we'll include addition value add services 
and features that you can tag on in a predictable manner but we never want to show you a fractional cost or making it difficult for 
you to understand what you're paying.

If you're using the Dev tier, its totally free of charge. We're using fair usage limits to make sure everyone gets their fair go of 
things and capping it at 1 core and 1gb of memory for all the services in your namespace. You can cut that up however you like. In the 
case of the Platform tier we're giving you 2x that with 2 cores and 2Gb of memory. In the future we'll make this configurable so you 
can top up as you need.

### Goals

Our goal is not to replace cloud compute or large scale infrastructure providers. This isn't something we can really do and infact they 
do such a good job of it we shouldn't have to. What we've however noticed is the developer experience is really lagging behind in 2020. 
Where Heroku took too much away, AWS is giving too much back. Especially to the developer. 

Our primary goal is to abstract away the complexity of the cloud and provide a new development model that focuses on distributed and 
multi-service development on top. Based on our experiences we think to do all that you really have to be focused on the developer UX 
for microservices and that requires a number of primitives listed in the feature set above.

Over time though we know some of those abstractions and the infrastructure components will require direct access and we want to promote 
the use of managed services in the various cloud providers as appropriate. So we'll instill a pluggable model and drop in replacements 
for anything we offer.

Overall we think developers are really in need of a new cloud platform, one that focuses entirely on their needs rather than overloading 
them with the need for infrastructure and operational management.

## Next Steps

We're excited to unveil M3O to the world and hopefully you're interested in trying it out too. Just head on over to the [website](https://m3o.com) 
to get started or join us on [slack](https://slack.m3o.com) and [discord](https://discord.gg/hbmJEct). If you've felt the pains of managing 
cloud infrastructure and want a simpler experience that just lets you focus on microservices development then we're the 
new cloud provider built just for you.

Cheers

Asim Aslam
<br>
Founder & CEO Micro
