---
layout: post
title: Why Programming? Why Python? Why Now?
date: 2013-12-30
categories: [blog]
permalink: why-practice-python
---

Programming is the missing link in education. It lets you explore, play, work with others, and fail in a safe environment. Everyone should learn to program.

<!-- more -->

## Programming is the Missing Link in Education

The goal of a modern education is to nurture a person to adulthood, someone who is capable of solving the tough problems of tomorrow. However, in schools we are taught to memorize and regurgitate. Most students don't come close to an exploratory, iterative, problem solving education. I want to tell you why programming is the best way to fill those gaps. No matter how old you are, programming practice is for you.

There are four [fundamental aspects of learning](http://ecologyofeducation.net/wsite/?p=2457) that are most effective:

1. Problem-driven and individualized
2. Fun
3. Safe from failure
4. Group engagement

(there are many more, but you can read any blog, article, book about educational philosophy and fill in the gaps yourself).

The idea is this: if you have a problem or a goal to reach, you are free to explore options and work with trial and error at your own pace. In an environment where failure is not only OK but expected and surrounded by others facing similar problems, you will not only be empowered to solve your small problem but also build enough confidence to solve larger problems. Sound a bit idealistic? Maybe so, but it’s a good practice arena for building up the intangible skills like confidence and problem solving. When faced with a real problem (that most likely has nothing to do with programming), you will have enough on your plate trying to figure out the right answer that you want your confidence and persistence backing you up.

Programming is the perfect sandbox. Remember back to your 5-year-old days playing in the sandbox. You were taken to another world, filled with ants and dunes and trucks and shovels. Nothing played by the rules of the outside, and whatever you did in the sandbox didn’t work outside the sandbox. You were the one who moved from in to out, and the only thing that remained consistent was your knowledge from inside and out. In the case of an educational arena, programming is our sandbox. The problems we solve inside the sandbox are not necessarily relevant to the outside world, but they are interesting problems in their own right. Figuring out that you need to push the truck harder in the same doesn’t apply to the pavement next to the sandbox, but solving this greatly enhances our intra-sandbox play. The purpose of solving these problems is not to advance the world outside the sandbox, but to advance yourself within the sandbox. Since you are then free to move between the sandbox and the outside world, the skills you build inside the sandbox are immediately transferable to any problem on the outside. Inside the sandbox when you are learning about time-sharing the best shovel with three other children, you’re secretly learning the skills of cooperating on a team. Programming exercises work the same way: you learn the process of solving a problem, and take this problem-solving knowledge with you when you finish.

Why is programming an effective education?

1. It is **problem-driven** and **individualized**. By definition, every program you write is solving a problem. Why? Because every program accomplishes a task - the problem is as simple as “I can’t accomplish this task.” For example, if I asked you to write all the factors of 10 on a piece of paper in less than 10 seconds, that’s your problem. Maybe this one is easy, but then I can ask you to do the same for the number 123456789 (still in 10 seconds). Not ready to solve that problem yet? Not to worry - there are plenty of easier problems out there waiting for you to solve them! Have an extra afternoon this week? Not to worry - you can do another problem! You can work at your own pace in solving small problems.
2. It is **fun**. The satisfaction of making your computer output text to you for the first time is pure joy - I still remember the time when my father taught me the “echo” command in the DOS prompt. I thought I was so cool.
3. It is **safe from failure**. Programming exercises are not mission-critical; if you mess up the first 100 times, no one is going to die as a result of your typo. No horrific droughts, no estrangements from relatives, no forest fires. You just take that you messed up and try again.
4. It is a **community**. Because there are countless others solving programming problems (in Python), you can always ask a question.

## Python is the Answer

When you start to learn programming, why start with Python in particular? A few reasons:

1. Python is industry standard. If you learn / master it and want a software engineering job, this is one step. Google and YouTube both have sections of their back-end software written in Python.
2. There is a large community of developers in Python. Sharing, commenting, looking at other's code is exactly the way to learn more. (See educational criterion number 4 from above)
3. There are scores of libraries written in Python to solve many tasks. There are new tools and libraries being developed every day, so you can automate any kind of task you can think of in Python. The fuzzywuzzy library implements fuzzy search; the Youtube-dl package lets you download YouTube videos; the this package shows the text of “The Zen of Python” on the screen; etc.
4. Python reads like English - if there is any language whose code you can look at and just read, it is Python. For example:

{% highlight python %}
    for number in range(-4, 5):
        if number > 0:
            print("positive")
        else:
            print("negative")
{% endhighlight %}

What does this program do? It looks at each number in the range of numbers from -4 to 5 (non-inclusive), then checks whether the number is greater than zero or not, printing a message according to that property. Look, English!

## Why You Should Learn to Program Now

For the average person, programming is the gateway to automation. For engineers, programming is one of many tools of the trade. For data scientists, programming is THE tool. Working at your own pace on small problems, with repetitions approximately weekly, you will train yourself in the art of problem solving and expand your confidence in solving ever larger problems. In your own ventures, in your own disciplines, in your own lives, you can make a difference.

## Getting started

Want to get started? Start with [Exercise 1]({{ site.baseurl }}{% post_url 2014-01-29-01-character-input %}), or visit our [resources for learners]({{ site.baseurl }}{% post_url 2017-01-15-resources-for-learners %}) page to find Python books, courses, and online resources to help you along your journey.