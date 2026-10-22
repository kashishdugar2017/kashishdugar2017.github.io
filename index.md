---
layout: default
title: My Coding Journey
---

# Hi, I am Kashish

I am 9 years old. I am a software developer and a competitive swimmer. I live in Kochi, India.

I build real desktop apps, games, and web backends using Python. Right now I am learning algorithms from **Grokking Algorithms** and reading **Code** by Charles Petzold to understand how computers work from the ground up. In January 2027 I am starting Rust.

This blog is my daily learning log — one post per day from the end of my 2.5 hour programming session.

My GitHub: [kashishdugar2017](https://github.com/kashishdugar2017)

---

## Posts

{% for post in site.posts %}
- **{{ post.date | date: "%b %-d, %Y" }}** — [{{ post.title }}]({{ post.url }})
{% endfor %}
