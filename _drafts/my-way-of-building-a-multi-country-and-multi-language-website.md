---
layout: post
title: "My way of building a multi country and multi language website"
categories: webdev
tagline: ""
tags: [coding, rails, global]
---

A few weeks ago, we decided that we wanted to have Traditional Chinese on our <a href="http://firstcodeacademy.com" target="_blank">First Code website</a> to cater to non-English speaking parents. Seeing our brand in Chinese is a significant milestone, yet all that I could think of was the amount of infrastructure and code changes we would have to make to accommodate that. Challenge accepted, let's make it happen. This is how I did it. Warning: long and geeky.

### List out the challenges

As a Software Enginner (on top of my COO role), I began to draw out a few implications.
<ol>
	<li>URL structure will be changed from hk.firstcodeacademy.com to hk.firstcodeacademy.com/en to indicate the country and the language the visitor chooses</li>
	<li>For text within the app, all the text strings are going to move from .html.erb files to .yml, we will not have one line of English in any html file anymore</li>
	<li>For text that are entered through admin panel, we will need a way to do translations on the model level and save in the database. The data has to be parallel in each language, and this could be the challenging part</li>
	<li>Set up redirection and locale switch</li>
</ol>

### Determine URL structure

### Start with country set up


### Time for data translation on ActiveRecord model

Once I figured out what I needed to do, the next step was clear that I had to tackle the hardest part, which was amending the database design so that it could accommodate translation. I did a ton of research and came across this article about <a href="http://www.apphp.com/tutorials/index.php?page=multilanguage-database-design-in-mysql" target="_blank">Multilanguage Database Design in MySQL</a>. It was well-thought-out, listing the pros and cons of the 4 ways of handling multilanguage on the database level. If I were to choose, I would have picked "Single Translation Table Approach". Despite that querying could be complex and the table could be hard to maintain in long run, its ability to keep all translations in one place appealed to me.

Just when I was about to dive into figuring how to set up the single translation table, I remembered it would be wise to always check out existing Ruby gems to see what other developers have created. The community has never disappointed, really. I found <a href="https://github.com/globalize/globalize" target="_blank">Globalize</a> and it was exactly what I was looking for. It uses "Additional Translation Table Approach", and with Rails migrations, it was a piece of cake.

### Build a translation admin panel

### Extract all the text strings
I'm serious. Sometimes developers do have to do a lot of tedious work.

### Implement Multilingual and Multiregional SEO

### Go to bed
