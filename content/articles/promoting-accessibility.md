---
title: How to successfully promote accessibility in your organization
description: Accessibility is a challenging part of design and development. It often feels like an arbitrary set of rules that stand in the way of exciting design and innovation. There's also a legal component and most developers are not lawyers. So how do you successfully promote its principles?
img: https://images.unsplash.com/photo-1573497019414-e44d0759d00e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1770&q=80
alt: ""
caption: "Accessibility is a team effort"
tags: ["accessibility"]
status: "published"
---

This can be very challenging. There's nothing like spending months of design and coding on an exciting new project and suddenly you're reminded that you need to do an accessibility assessment before going live. The report comes back and it's pages and pages of confusing bad news. The color contrast of some of your buttons is not sufficient, some pages don't mean a success criterion called "Meaningful sequence"? What is going on?

You don't need your entire to become accessibility expert. It's a massive subset of the field and even experts today are constantly learning new tricks or new quirks. Although there are tools you can use to help and automate some of it, you still need people with the right instinct and mindset to properly determine if your website is compliant. So where do you start?

## Web accessibility is first and foremost about humans

Humans should be at the heart of everything we do. I've heard accessibility described as "something the blind people need". This is a common myth, but in fact accessibility is about everyone. Everyone benefits from a more accessible website. When I did my first accessibility training, we met with people with various disabilities and they explained how they use their computer. Someone was using a screen reader who would read the page content so fast all I could catch was a few words here and there. Someone else used a device that allowed them to read the page in Braille. Spending a part of our day with them was a big revelation. The following video highlights some examples.

<youtube-embed url="https://www.youtube.com/embed/3f31oufqFSM"></youtube-embed>

To try develop the required instinct, I suggest the following questions to help think this through. Those are not technical questions in any way. The point is more about creating self-awareness and think a bit more about how you use a website.

### Question 1: Am I dependant on a specific sense for something?

An example I like to use is a spreadsheet with a list of orders. Some rows have green or red text. Green means the order was completed and red means it was cancelled. This is explained in the spreadsheet because at the top the word "Completed" is green and "Cancelled is red".

Ok, but now I just printed it and it's all black and white and I don't know what is what. But even on a screen this is not ideal. Sure, people with monochromatic vision (people who perceive the world in shades of gray), is extremely rare, but wouldn't it be better to add a column with the order status and the word as a value instead? If I would just read the text of the row to you, you'd have no idea this order is complete. Which is what a screen reader would do. So having a column value for it would make sense anyway. This would also allow you to sort rows by order status, filter out completed orders etc. The benefits are clear here.

How about sound? Do you have a video on your website about the latest announcement for the company but no transcript or subtitles? Why not? It's not terribly expensive to do. Currently, my entire team is working remote and an employee is deaf. He's using the live captioning feature in Microsoft Teams and I don't think they could work without it. Sure we have emails and messages, but imagine being excluded from a whole category of communication. You'd lose so much information and context.

Here's a fun exercise. Have you tried that feature? [Here's how to enable live caption in Microsoft Teams](https://support.microsoft.com/en-us/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260). Give it a shot in your next meeting. If you do, you'll notice a few things:

1. Microsoft Teams can add the name of the person currently talking. Which is really cool. It helps put an identity to the words instead of melding all of them together.
2. It's terrible if people talk at the same time and there's quite a bit of delay between the words spoken and the text appearing.
3. It's currently useless in bilingual meetings. I'm sure this will get better at some point and I hope my current department allow the update to go through. This would actually be helpful for a lot of people.
4. It's terrible with abbreviations. This might make you self-aware about how many of them we use in a sentence.

A final example I like to give is of a bar chart. You're making a report and on one of the page there's a big chart that shows the number of hours in the last 12 months spent on various tasks. So what do you do for the alternative text? Maybe you can put the conclusion the chart is trying to convey visually. Something like "December and July have on average less hours spent in meetings". But what about the rest of the information? I was interested in a different data point. The best solution is think in text first, and in this case, a chart is basically a fancy table.

### Question 2: Can I do everything using only a keyboard?

This one is a bit tricky because you, the person reading this, might be using your mouse all the time and not know how to use a keyboard to navigate a whole website. It's actually easy and is actually helpful to prevent repetitive strain injuries and will help you think better about the importance of keyboard accessibility.

Sometimes I'm booking a hotel room for a trip and I wish I could just type the date instead of clicking a bunch of time to find the dates. Wouldn't it be easier anyway?

### Question 3:
