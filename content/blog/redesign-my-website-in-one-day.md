---
title: "Redesign My Website in One Day"
date: 2017-08-13T15:59:09+08:00
draft: false
---
Last week, I started positioning myself as a freelance front-end developer, not a general web developer. I want to focus on building stuff with my coding skills not using page builder to build a website. I didn’t feel excited working using this stuff; I only make it for money, not passion. One day, I try to submit my website into google page speed, and the page load is **8s - 10 seconds**. Oh shit. I saw through google developer tools, and there are tons of request and unoptimized images. Have thought of managing too many plugins on WordPress.  

![Old EpalValley speed](/image/20170813/ev_old.png)

Since my website was using page builder and the purpose of the site didn't look same with my vision. I decide to redesign my website in one day. I kind of procrastination person, that’s why I choose to set a deadline. Assume this as a marathon.

To make this accomplished, I need to list out objectives of the website and decide what I need to do to reach the objectives

1. Present my vision as a solo freelancer, not agency
2. Narrow my niche into front-end development. I do PSD conversion into HTML or WordPress and custom WordPress development.
3. The website needs to be fast. 10s is too long.
4. It needs to have a blog section and contact page at least.

I decide to not to use any WordPress themes for this marathon. Since I do front-end development and I want to prove my skill in building a website from scratch. I do a lot of research at dribbble,  [Behance](http://behance.com), [Web Design Inspiration](http://www.webdesign-inspiration.com), and [Landing Folio](http://www.landingfolio.com). I sketch my notebook how my site will look alike. There is 3 type of pages I need to do which is home page, about and contact.

For the **homepage**, I need to have section to tell who I am and what I do, several works, services provided and call to action at the bottom.

For the **about**, just a paragraph that tells how I got started in this niche.

The last one is **contact**. This page needs to have all of the contacts information to reach me. I have setup calendly to help user to schedule meeting with me.  

I start doing the front-end using [Bulma framework](http://bulma.io/) and SASS as my preprocessor. I like how Bulma use flex to positioning element and it's quite light. I write all of the code in Visual Code Studio, and I fall in love with it. Never going back to sublime. It’s free, fast and a lot of plugins. Most of my images are using SVG now for better performance, and I used [Koala](http://koala-app.com/) for Windows to compile, auto prefix and minify my SASS file. If the images were in PNG or JPG, I would resize until maximum usage. For example, if you are only using 300px * 300px on the website, you don’t need to have 1200 * 1200 px. To compress the images without losing the quality, I’m using [Tinypng](http://tinypng.com).

![Bulma Framework](/image/20170813/Bulma.png)
![Sass Preprocessor](/image/20170813/SASS.png)

After working on on the static site and fix bug on mobile responsive, I just realised I need to make a blog page where I share all of the articles (including this one). After several research on Google, there two options that may interest me which are WordPress and Hugo. I have works with several WordPress website previously, so it didn't take so much of my time.  Since, the time is still early, I decide to learn Hugo for my website. [Hugo](https://gohugo.io) is a static website generator likes Jekyll but it’s using GoLang.

Thanks you to the [Hugo documentation](https://gohugo.io/documentation/), it’s so easy to setup on my Windows machine. After googling sometimes working on some bug, finally its working!

![HUGO](/image/20170813/hugo.png)

I like how simplicity the Hugo directory arrange the file of the website. The blog is written using Markdown, so there is no interface, and most of the job is done in the terminal. I start working on integrating my static site into Hugo site while learning from the documentation and googling random site. After several hours, it's done and ready to deploy.

One another problem is where I need to host this website? I only have shared hosting, and it doesn't support Hugo. I found [Netlify](https://www.netlify.com/) my suitable for me.

![Netlify Interface](/image/20170813/Netlify.png)

The reasons I choose Netlify are
* It's fast
* Automatic Deploy
* Include CDN
* FREE

Now, this is a new thing I need to learn. There are many tutorials on Google on how to setup Hugo in Netlify. Go googling boys. My website files were host in Github and compiled using Netlify.
By the way, Netify gives a free SSL by Letsencrypt, and it’s easy setup. After pointing my domain into the Netlify Server, the propagation took several hours to fully working.


## Result


![New Epal Valley Page Speed Result](/image/20170813/ev_new.png)


After several tests on the different website to measure website speed is around 2 - 4 seconds. It was a tremendous performance. It’s a static website no wonder it’s so fast.  Take a look at my website [Epalvalley](https://www.epalvalley.com).


## My future plans


* Add mailing list
* Add custom post type for my works
* Add comment on blog post  
