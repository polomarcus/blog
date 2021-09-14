---
title: "I Suck At Whiteboard Interviews"
draft: false
description: "And  I am ok with that, but my dream job’s company wasn’t"
date: 2017-07-07T14:41:06+02:00
---
*Also published on [Medium](https://medium.com/@polomarcus/i-suck-at-whiteboards-interviews-809e9927d2d6)* 
Nowadays my main objective is to find my dream job, why? Simply because I am young, don’t have any kids, don’t have any loans, and I think I have the right positive energy and knowledge to work on everything, so why not focus on these kind of jobs?
I’ve recently done interviews for Spotify in their Stockholm office for a Data Engineer position thanks to 2 blog articles ([first](https://medium.com/@polomarcus/analyze-one-year-of-radio-station-songs-aired-with-sql-spark-spotify-and-databricks-835fcf73df6), and [second](https://medium.com/@polomarcus/music-recommendation-service-with-the-spotify-api-spark-mllib-and-databricks-7cde9b16d35d)) I wrote about their API. I had my first video interview in March 2017 and my last on-site interview on May 31st.

![Stockholm, Sweden (credit Unsplash)](https://cdn-images-1.medium.com/max/1500/1*gwe2Kiq_Z_Z6ECfgyXdO5g.jpeg)

Why I consider this position as a possible dream job:
* They’ve worked a lot [on their engineering culture](https://vimeo.com/85490944)
* Excellent reads on [their tech blog](https://labs.spotify.com/), meaning that you can collaborate with one of the best engineers and learn from them
* They used a managed solution on the Google Cloud Platform, which means spending more time on your product and less time managing serversÂ 
* [build the tools to work efficiently on top of GCP](https://github.com/spotify/scio) and [use new tech](https://beam.apache.org/get-started/beam-overview/) for defining batch and streaming data processing jobs

This kind of job makes you grow as a engineer.

# Preparation
I’ve read ton of articles, read [Martin Kleppman’s “designing data-intense applications”](https://library.oreilly.com/book/0636920032175/designing-data-intensive-applications/26.xhtml?ref=toc#idm140605782689984), [Holden Karau’s “High Performance Spark”](http://shop.oreilly.com/product/0636920046967.do), tried a lot of new tech, presented [my first talk](https://www.slideshare.net/PaulLeclercq2/analyze-one-year-of-radio-station-songs-aired-with-spark-sql-spotify-and-databricks) at 2 Meetups, thanks to the interview pressure I felt.

{% twitter 483688700447326209 %}
<center>*The more you know the less you know, Trump version*</center>

I also had a few technical interviews with others companies to practice my presentation skills, *well… that’s the game and also you might get lucky enough to find excellent opportunities*, where I was sometimes weirdly questioned about stuffs I learned during my computer science studies: [how collisions are handled within a hashtable](https://stackoverflow.com/questions/4980757/how-do-hashtables-deal-with-collisions/4980797#4980797), or exercises about [Linked List](https://www.interviewcake.com/concept/python/linked-list?). I spent a lot of time to prepare for it, it made me a better engineer, and it feels good.
I’ve also noted everything I could while doing interviews, to be sure to work on my weak points for the next ones.
Also to boost my confidence, just before my on-site interview, I spent the whole day at the National Library of Stockholm studying for my interview that will take place the next day.

![Stockholm, Sweden (credit Unsplash)](https://cdn-images-1.medium.com/max/600/1*sN6zs7mGAG2wIi91T1V2nQ.jpeg)


# On-site Interviews
I got welcomed by the HR I had on the phone, he explains me kindly what was going to happen and how I should act during interviews. During chit-chat he asks me how I was, I sincerely answered him that I felt stressed and that’s I didn’t have much sleep the night before, but I was really excited and curious about these interviews.

They use easygoing-style interviews to be sure you act normal as possible, or at least the most normal you can, in front of a whiteboard. A lot of smile, soft drinks, bathroom breaks invits…

## Programming interview and SystemÂ design
I’ve always have this weird feeling when I got asked something that the interviewer know, actually I have the same feeling when I speak English to a French-speaking person that speaks better English than I do. The advice I have, and that I have trouble to follow, is to imagine you want to explain your solution to one of colleague that doesn’t work in your team, as a data engineer, for example a front-end developer: he has the potential to understand it, but hasn’t spent as much time thinking about it as you have.
So we’ve talked about how we could design a real-time dashboard for the most played songs, and an exercise about removing duplicates from a list while maintaining the order. I’ve had this great feeling that I’ve almost done everything right when going out of these interview, and it gave me confidence for the others.

## Lunch
I had a one-hour break, that I thought I was going to spend alone, so I took a book with me, but actually, the Engineers that were my interviewers for the day ate with me, I really enjoyed it, and I felt like a true team member, even for one hour.
*Fun anecdote: I once got interviewed by a huge company, where my 2 interviewers, that have apparently already eaten, couldn’t leave me alone while I was having my lunch, so I had the strangest lunch of my entire life, where 2 people that you don’t know try to make small talks while watching you eating.*

##Culture interview
I would rather had a written culture interview, because some questions cannot be answered without thinking them throughÂ : what is the best advice you gaveÂ ? *Hmm.. Well.. Exercice and eat healthy, I guess?.* Other questions were what is a team? What is a successful one? And you should answer these questions with concrete examples.
I try to be honest when answering these questions, for example I said that I need a team to backup the solution that I propose otherwise I don’t feel 100% sure. But I guess it can be quite easy to embellish answers. My advice would be try to do so, because that’s simply the interview game.
Another advice, you should have no doubts in which team you want to work with, every answer you give should say, I am the right fit for this particular team. To know this, you need to do your homework by looking for on LinkedIn what people actually do in their team.

## Case study interview
With a real-life problem they had, they want to know how you would debug the problem that is hidden somewhere inside monitoring tools. It was a role-play kind of interview, and by the end he had fun with the 2 interviewers. One of them knew that I’ve built the #1 online alarm clock. It feels good when interviewers know your profile, you can say that’s a obvious thing to do when interviewing people, but it’s really rare. You would be surprised by the number of times I had to present my profile during different interviews at the same company, this is one of the reason I currently feel a fatigue of interviews, although I love talking about data engineering. One time on a 5-hour on-site interview, I had to answer to a question that has been asked to me at a previous interview on the same day, even if I told the interviewer that I’ve already been asked this, he suggested me: try to give a different answer. After the on-site interviews, I knew I won’t accept any jobs there.Â 
Some advices I would give to interviewers, please be agile and act as an human being, as every interviewee is different.

## Results
After 5 hours at the Spotify’s office, being interviewed, I felt weirdly great and full of energy, meaning that I had good times. I summed up my day with the HR I met when I arrived at the beginning of the day, and he proposed me very nicely to visit the whole office: I’ve never seen some many microwaves in my life haha
2 days later, after discovering Stockholm, the city where I was going to move because I did so great, I received this email from the same HR

> I am sorry that I have not been able to get in touch earlier with the outcome of the onsite. It took longer than expected. Unfortunately, I have to let you know that we will not proceed with you for this role.

![Boy, that hurts](https://cdn-images-1.medium.com/max/600/1*4xR6bhFYug1LMRArIP7N0Q.jpeg)

He also offers me to go through each interview by phone so that I can understand their final answer. It was really appreciated. To sum up their decision, I tend to lack of confidence, that I don’t feel sure when I explain my solution. But I guess this is what  whiteboard interviews is all about, see how you can handle a new problem without your usual tools, a proper amount of time to check your different solutions and 2 people observing all your movements. I would had loved to be asked a bit more about the solutions I presented to show that I could answer, most, questions. But also, to confort me, the HR told me that all interviewers said that I was friendly, *it’s a good point for Gryffondor, I guesss?* And he also gave me hope that I could be a good fit in one year.Â 


# My thoughts on 5-hours on-site interviews
The on-site interviews happened after being selected among a tons of CVs, two 45-minute phone/video interviews with HRs and engineers to make sure you can fit the role they offer, and a 1:30 hour video technical interview with 2 engineers. If we sum the hours spent with the on-site interviews, it’s 8 hours.
If I compare that with my experience of working with new hires, I could say in 30 minutes if the person knows how to code, if I will get along well with him/her, and most importantly, if the person is passionate about what she/he does. **[How could we need 8 hours to see that](https://medium.com/javascript-scene/tech-hiring-has-always-been-broken-heres-how-i-survived-it-for-decades-b7ac33088de6)?**

Although I had a great time being interviewed at Spotify, I have to say that for a second I couldn’t help feeling frustrated and seriously thinking about questioning my professional skills. Especially when you think you are going to get an offer because you were quite happy with all the answers you gave, and sometimes even proud. And also when you went to the extra miles by writing 2 show cases of your skills based on their API.

On the other hand, *how would you handle 10 000 applicants for a position?* You have to select on details, like Spotify did with me, and I can totally understand that.

In my opinion, on-site interviews should be casual, no code needed, as they’re done during video-interviews. Only case study ones or architecture design to see your point of view on different subjects and what you could bring to the company, with the whole team you are being interviewed for, followed up by a comfort meal all together to be sure that you can fit well among the team.

# Try.
To finish this article, and encourage you taking a proper amount of time to apply for your dream/better job,have a look to [this quote from Ben of the Practical Dev](https://dev.to/ben/embrace-how-random-the-programming-interview-is)

> But if your goal is to land your dream jobâ€Š–â€Šor just get your first jobâ€Š–â€Šplay the game and take more risks. It is up to the hiring firm to disqualify you, it’s not your job. Somebody is going to be the benefactor of randomness, it may as well be you.


