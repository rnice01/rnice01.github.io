---
layout: post
title: "Starting My Cybersecurity Journey (with Rust... and a Little Help from AI)"
date: 2025-05-25
tags: [cybersecurity, rust, ai, learning, personal]
author: Rob Nice
description: A developer's journey from Elixir to Rust, diving into cybersecurity with a little help from AI.
---

One of the things I love most about working in tech is how fast the field evolves. There’s always something new—new tools, new threats, new ways of thinking about systems. That constant change is exciting… but also overwhelming. I’m someone who loves learning new things, but sometimes it feels impossible to narrow down what to focus on when *everything* looks cool.

Lately though, I’ve found myself drawn more and more toward cybersecurity. I currently work for a cyber insurance company that provides threat intelligence and alerting services. My team focuses on a data aggregation system that feeds our dashboard with findings about our clients' systems. It’s rewarding work—we don't just detect risks, we help educate our clients about the vulnerabilities we surface and what they can do about them. Even when we don’t end up insuring someone, we still try to help. That part of the job—*the protector role*—is what drew me to the company in the first place.

## My Stack (and Why I Love It)

We use a combination of [Oban](https://hexdocs.pm/oban/Oban.html), an Elixir-based job processing library (think Sidekiq but for the BEAM), along with Python-powered AWS Lambda functions orchestrated with Step Functions. Everything communicates via SQS. Lately, I’ve been doing more with Python to rework some of our Lambda architecture, especially since the original implementations didn’t scale well. I’ve been experimenting with [asyncio](https://docs.python.org/3/library/asyncio.html) to address performance bottlenecks.

Elixir and Oban are an incredible combo for building scalable, resilient systems. You get out-of-the-box features like job dependency management, concurrency, and rate limiting—which is critical for us since we rely so heavily on third-party vendors to flag vulnerabilities.

I genuinely love my job, and I’m excited to keep growing in this field. But I want to go deeper. I want to understand how threats are discovered in the first place. How is that data acquired? Can we build some of those tools ourselves? Could we eventually move beyond detecting threats for underwriting purposes and start building defenses?

## So Why Rust?

I’ve dabbled in Go and Rust over the past few years, but I always end up retreating to Elixir—my comfort zone. Systems programming languages like Rust intimidated me. I didn't feel like I had the right background, and I wasn’t sure where to start.

Then I had a thought: *What if I asked AI for help?*

So I typed:
*"Hey, I’m an Elixir developer. I know web stuff, but I want to learn cybersecurity and Rust. Can you help me?"*

And the response floored me.

It suggested a roadmap, helped me narrow my focus, and emphasized how broad cybersecurity is. That made it clear: I needed a direction, not just curiosity.

We broke down the field into themes like defensive programming, security testing, and ethical hacking. I asked for a 6-month roadmap—and it gave me one. Each month with a theme, each theme supported by a project. That’s how my current project was born: building a tool that can monitor my own network for potential threats and alert me in real-time.

## The Kanshi Protocol

Then came the fun part: naming the project.

I told the AI about my interests—Warhammer 40K Space Marines, World of Warcraft Paladins, and Japanese culture. We explored name ideas until something clicked: **Kanshi Protocol**.

> *Kanshi* (監視) is a Japanese word meaning "to watch over."
> "Protocol" gives it a systems/security vibe.
> Together: a guardian always watching, ready to act.

The AI suggested branding it. We brainstormed a logo and tagline. A few iterations later, the logo you see on this page was born.

## What’s Next?

My next step is to build my first Rust-based security tool and keep diving into topics like threat intel, mitigation strategies, and network security. I’m still learning—but now, I’m not doing it alone.

AI has its limits. I don’t blindly trust every line of code it spits out. But having a patient, judgment-free assistant to bounce ideas off of and ask “dumb” questions has made a huge difference. I feel empowered to tackle topics that used to intimidate me.

I hope to keep blogging about this journey—not just to document it, but to hopefully encourage others who are on the fence about diving into cybersecurity or learning a lower-level language like Rust. You don’t have to go it alone.

Let’s see where this road leads.

---

*This post was drafted by me and edited with the help of ChatGPT.*
