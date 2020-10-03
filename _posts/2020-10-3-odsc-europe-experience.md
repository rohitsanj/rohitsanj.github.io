---
title: Sharing my experience of attending ODSC Europe 2020 🌍
layout: post
---

I had the privilege of attending [ODSC Europe](https://odsc.com/europe/) from September 17th - 19th, 2020. I was given a 4-day pass from the team at [JovianML](https://jovian.ml), and I am ever grateful to them for giving me this opportunity. Thanks Vishal and Aakash!

![ODSC-Certificate](https://i.imgur.com/bYEp2fb.png)

## The ODSC Live Platform 🔥

I have to write a whole section about the online platform where the conference was held because the page we are greeted with soon after signing in, is a life-like animation of how the conference would have looked like if it were happening offline. Here is what it looks like:

![ODSC gif](https://odsc.com/wp-content/uploads/2020/04/odsc-europe-360x640-2.gif)

And, here is what the virtual lobby looks like 👇

Note that this is just a screenshot, you can actually see them moving around. Trust me when I say that it feels _extremely_ life-like. A much needed thing in this pandemic situation!

![Virtual lobby](https://i.imgur.com/WpE46pq.jpg)

## Some of the sessions I attended

### SQL for Data Science - Mona Khalil, Data Scientist at Greenhouse Software

The conference began with the training sessions, of which I attended [SQL for Data Science][sql-data-science]. I have not had any formal training in SQL, and hence this session really helped me solidify my SQL knowledge. It also made me realize that I can become a better Pandas user if I know how to write SQL queries well!

### MLOps: ML Engineering Best Practices from the Trenches - Sourav Dey, Manifold and Alex Ng, Manifold

I found this workshop to be extremely useful because it gave me an insight into how actual machine learning or deep learning enterprise projects are developed and deployed. The workshop was co-presented by Dr. Sourav Dey, CTO at manifold.ai and Alex Ng, Senior Data Engineer, manifold.ai.

Dr. Dey talked about how machine learning looks great in principle, but its real business value arises from machine learning in production, where it is solving real customer use cases. He identifies that putting machine learning into production is _hard_ - and mentions two types of complexities:

- Inherent complexity: The problem _itself_ is hard.
- Incidental complexity: The decisions made by the data scientists or machine learning engineers early on with respect to development evironments, and such - can make deploying models really hard later on. You might even call it as "ML Engineering Technical Debt".

Alex then takes the stage and talks about how Dockerising all environments early avoids all aforementioned problems.

Key takeaways from the session:

- Learnt about different roles in an AI team
  ![](https://i.imgur.com/mreV0re.png)
  ![](https://i.imgur.com/RNVZDt3.jpg)
- "Use docker on day one - It makes everything easier right now and downstream"
- Leverage software engineering principles and workflows into machine learning workflows - version control, unit testing, code quality etc.

### In Conclusion

I would like to thank all the organizers and volunteers of ODSC Europe for conducting this conference. Hopefully, I will be able to travel to Europe next year to attend the following edition of the conference.

---

Thanks for reading!

<!-- Links -->

[sql-data-science]: https://odsc.com/speakers/sql-for-data-science/
