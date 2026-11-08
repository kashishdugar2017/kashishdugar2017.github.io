---
layout: default
title: My Coding Journey
---

# Hi, I am Kashish

I am 9 years old. I am a software developer and a competitive swimmer. I live in Kochi, India.

I build real desktop apps, games, and web backends using Python And now Rust. I have finished `Grokking Algorithms`! Now i am Learning Rust using the book `The Rust Programming Language` and reading `Code by Charles Petzold`. I am also reviewing existing codebases once a week


This blog is my daily learning log — one post per day from the end of my programming session.

My GitHub: [kashishdugar2017](https://github.com/kashishdugar2017)

---

## Posts

{% for post in site.posts %}
- **{{ post.date | date: "%b %-d, %Y" }}** — [{{ post.title }}]({{ post.url }})
{% endfor %}
