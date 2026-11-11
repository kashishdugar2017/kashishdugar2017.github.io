---
layout: default
title: My Coding Journey
---

# Hi, I am Kashish

I am 9 years old. I am a software developer and a competitive swimmer. I live in Kochi, India.

I'm learning how computers work from the inside out, from algorithms down to the bits underneath. I build everything from scratch in Python and Rust, using one method: make it mine, paper first, then code.

This blog is my daily learning log — one post per day from the end of my programming session.

My GitHub: [kashishdugar2017](https://github.com/kashishdugar2017)

🌙 Moonlight, building with Papa and Mumma (and Agastya later) for the Startup Buildathon: [Moonlight Build Log](/moonlight/)
---

## Posts

{% for post in site.posts %}
- **{{ post.date | date: "%b %-d, %Y" }}** — [{{ post.title }}]({{ post.url }})
{% endfor %}
