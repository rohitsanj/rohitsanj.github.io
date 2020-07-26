---
layout: default
title: Google Summer of Code Blogs
---

# Testbook - Google Summer of Code

You can find all my Google Summer of Code 2020 blogs here.

<ul>
    {% for post in site.gsoc %}
        <li>
            <a class="post-link" href="{{ post.url | relative_url }}">
                {{ post.title | escape }}
            </a>
        </li>
    {% endfor %}
</ul>
