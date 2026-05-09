---
title: "Cross-Cutting Concerns Are Back, and the AI Stack Is Abusing the Gateway Pattern"
url: "https://traefik.io/fixing-ai-cross-cutting-concerns-with-gateway-pattern"
date: "2026-05-07"
author: "Immánuel Fodor, Sudeep Goswami"
feed_url: "https://traefik.io/rss.xml"
---
Some architectural problems do not stay solved. They come back every time the system grows by an order of magnitude, with the same root conditions in a more demanding form. Cross-cutting concerns are one such problem.They were named decades ago, in the era of aspect-oriented programming. They were resolved at the network layer over the 2010s, when API gateways absorbed authentication, rate limiting, observability, and policy enforcement from every microservice and moved them into a shared infrastructure layer.
