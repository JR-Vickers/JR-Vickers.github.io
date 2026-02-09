---
title: Building ML Projects with Cursor
date: 2025-07-17
description: Lessons learned from using Cursor for machine learning projects
---

I've used Cursor to work on a few machine learning projects so far, and I've learned many things about its strengths and its limitations. I decided to write them down and share them. Some of these techniques are well-known, but I've run into some shortcomings that I haven't seen discussed elsewhere. My sense on coding agents is that there are a lot of inexperienced programmers that don't have the context to understand their shortcomings, and that more experienced programmers just compensate for these shortcomings on their own. I've seen many senior devs criticize coding agents, but they rarely do a good job of explaining their position to less experienced people. My aim is to fix this.

Let's first talk about what coding agents are good at. Right now, the thing that they are best at is producing code that compiles.

This answer might surprise a few people. Most people think about coding agents in terms of the output code's functionality.

A useful principle of automation to understand is that it is easier to automate tasks that are easy to verify than tasks that are difficult to verify. "Does this code compile successfully" is much easier to verify than "is the learning rate on my binary classifier too high?" As a result, coding agents are better at the former than the latter.

---

One problem that I've run into many times with AI-generated code is efficiency. When I worked on the [OpenAI-to-Z Kaggle competition](https://www.kaggle.com/code/bjrnste/path-to-the-amazon-sun-gods#2.-Download-the-Terrabrasilis-deforestation-data-&-Define-the-AOI-around-the-Indigenous-Territories-uncovered-above), I was asked to use OpenAI's models in the process. For one task, I ran an image classification query on 30,000 satellite image tiles. I asked Cursor to write a script for this. The code worked! It successfully sent queries off to OpenAI. The only problem was that it was going to take half a week to get through them all. It processed one image every few seconds.

This intuitively felt wrong. OpenAI's developer docs said I could make up to 5,000 API calls per minute, so the problem must be on my machine. I read through the Cursor's code, and I saw that it was sending only one query at a time. There was zero batching or parallel processing of any kind. After manually rewriting the code, I was able to reduce the process from days to 15 minutes.

There are other efficiency-related limitations that Cursor doesn't integrate into its output, unless specifically requested. When writing programs, there are often a thousand ways that the programmer could, theoretically, write the code to get the desired output. However, some solutions are much less efficient than others. This may not matter is you're doing something simple, like building a simple website in raw HTML or CSS. But if the task is, for example, performing vectorized operations on arrays, the NumPy library offers a 10-100x performance increase over standard Python. For big data processing tasks, that can make a huge difference.

It's good to sanity check your work from time to time. If your program takes forever to run, it might be time to think about performance optimizations.

---

Another limitation I've encountered is that Cursor's fluency with different developer tools fluctuates wildly. For popular languages and libraries with vast amounts of training data, it performs very well. For niche libraries, it often makes mistakes. In the OpenAI-to-Z challenge, I utilized several satellite and map-related Python libraries such as geemap, geopandas, folium, rasterio, and more. The amount of training data on these libraries is often orders of magnitude lower than something like React, which significantly increases Cursor's error rate. For these libraries, I found it faster to just read the documentation and write code manually. Coding agents don't eliminate the need for documentation, they just push it out from the center. Instead of programmers spending much of their time reading documentation for basic, bread-and-butter libraries, they'll spend more time reading niche documentation.

If you're using uncommon tools and you keep running into errors that Cursor can't fix, you might just need to write those sections manually.

---

Cursor also has a poor track record with security. We've all seen the tweets of people pushing their API keys to GitHub because they didn't keep an eye on Cursor. I've made it a habit to handle all security manually. I spend a lot of time looking at and updating my .gitignore file, and I handle anything involving API keys manually. Before I push to GitHub, I run *git status* and verify that no sensitive files were improperly modified.

For now, security should not be outsourced to machines.
