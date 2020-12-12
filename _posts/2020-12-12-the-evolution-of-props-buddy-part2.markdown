---
layout: post
title:  "The Evolution of Props Buddy - Part 2"
date:   2020-12-12 12:00:00 -0400
categories: blog propsbuddy
---

## Superbowl LII - February 4, 2018
Things get technical. Introducing RyDog Sports Book, a name play on Bodog. Much like its name, the first iteration of the app was very much a work in progress. The first iteration was a locally hosted app, with hardcoded values everywhere, last minute hacks to get things working and a localhost address. In the fall of 2017, I began working on my pet project for several reasons:
- Make the annual props process more efficient
- Flex my nerd skills to my buddies
- Most importantly, to improve my technical skills. This allowed me to focus on areas that needed improvement for work that had been raised through peer review suggestions or just personal comfort level in areas.

The stack that I chose heavily reflected the stack that I was working with at work at that time.
- Frontend: AngularJS 1.x
- Backend: Java Spring Boot
- Databse: Postgres

Areas that I wanted to focus on were my UI design and database design. However, I quickly learned, that although I could easily add new controllers and services to my Java server, creating one from scratch was a whole other beast. This exercise drastically improved my actual knowledge of Spring, rather than just turning a blind eye to how it worked.

Little did I know that I would be referring to my own props buddy code down the road when working on things at work (i.e. auth module).

The result of a few months of off and on work was a locally run server hosted off my laptop. I entered the props in manually directly into the database. This version supported a single game only and just pulled all the props in the DB.

 
Back to the day of the superbowl, I had held the cards close to my chest on this one hoping to make it a surprise. Everyone passed around the handful of devices on my local network and entered their picks as they rolled in.

The end result of the props match was for the most part a success. A few live patches to address issues that arose mid game, but for the most part things went much smoother than the manual process and my friends were impressed with my hacked together solution.