---
title: What is this blog even about?
description: The main purpose of this blog is to be an outlet. I like to write and talk about a bunch of stuff including role-playing games like Dungeons & Dragons, public service (I'm a public servant) and coffee.
authorcard: false
---

# What this blog even about?

The main purpose of this blog is to be an outlet. I like to write and talk about a bunch of stuff including role-playing games like Dungeons & Dragons, public service (I'm a public servant) and coffee. I got sent a few products to review by publishers, but at some point I was not happy with Blogger and just deleted the whole thing. Yes, I'm old enough to remember Blogger.

As recently as 2020 I created another one using [Ghost](https://ghost.org/). I'm a web developer, but the idea was to jump in, focus on the writing part and go from ideation to execution as quickly as possible. To be fair, this is indeed the model I'd normally recommend. You want to write? Write. Use whatever you can and just get it done. You want to run? Just put on some shoes and start running. You can figure out better shoes and the rest later. I have a tendency to get stuck on the analysis part and never getting it done. So using something like Ghost was my solution. The minimal maluable product (MVP) was something I can use to write and customize to my liking. But I got bored and after reading <a href="https://www.joshwcomeau.com/blog/how-i-built-my-blog/">Josh Comeau's post on how he built his blog</a>, I decided to start from scratch.

## How I made this

I'm still working on it so I'll update the list as I go, but for now this is the overall stack.

### Vue 3 and NuxtJS

I really like Vue and React, but I know Vue better and <a href="https://nuxtjs.org/">NuxtJS</a> is fun to learn. If I would have used React, Next would have been the obvious choice. I'm using the `@nuxt/content` module and write my blog posts as Markdown. I can also add custom Vue components inside my markdown if I want. It's great. For me, that's much more convenient than setting up authentication, a database etc. I'm still learning a great deal about Nuxt, but so far I
like it.

### Tailwind CSS

[Tailwind CSS](https://tailwindcss.com/) is, by far, my favourite CSS framework. My first impression was a very common one: "Why
would you essentially do inline styles?". The problem Tailwind solves for me is the fact that working with CSS is usually a terrible developer experience. If you're using Vue or React, I highly suggest you consider using Tailwind. The utility-first flow is magical. I'd rather write components with utility classes than manage big CSS files. If you do write reusable components, you'll end up with manageable components <em>AND</em> manageable styles. Just by looking at the `class` attribute, I know what this is gonna look like. I don't have to find the classes in the stylesheet and hope nothing overrides it. In that sense, I don't think [BEM](http://getbem.com/introduction/) solves anything.
