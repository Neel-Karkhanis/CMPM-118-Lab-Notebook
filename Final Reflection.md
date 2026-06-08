# Week 10 - Final Reflection

## What I Did This Quarter:
- Read chapters 1-21 of the Rust Programming Language Book (RPLB), Brown Edition
  - Learned all the Rust basics, such as syntax, and on top of that, what makes Rust special, such as the memory guardrails and guarantees the language provides
  - Took quizzes that were embedded throughout each chapter to supplement what I was reading
  - My personal feelings toward the book were slightly negative, not due to the content of the book, but how the book was used to structure the class. I will go more in depth about this in the course feedback
  - During chapters 12 and 21 of the book, there were two projects which I worked through and got done: a Command Line Program and a Multi-threaded Webserver. These two projects helped give hands-on experience with programming with Rust, which just reading the book otherwise would not have
  - However, due to the formatting of the projects, where they followed a more tutorial-style project description, it wasn't as useful as it could have been. The projects were laid out in a way where you were following an already given plan and even source code to use to complete the projects, so instead of the projects reinforcing programming skills, it was more like reverse engineering what was already given to us
- Completed Rustlings Topics 1-23
  - Debugged several different programs that would relate to the week's current RPLB reading. Helped supplement what we were reading with actual code we had to understand and fix
  - A lot of the time though, the Rustlings were easily brute-forcible, and just following the compiler instructions would solve the issue, making them not as effective in practice
- Documented Each Week's Work/Reflection
  - Each week, I wrote a .md reflecting and summarizing the work I had done in each week
  - I also added a goals and tasks section, which briefly went into what was going to happen next week
- Read Research Papers
  - In around the second half of the class (weeks 4-10) we began reading research papers that related to Twizzler to give us new perspectives
  - The two papers we read were "Arrakis: The Operating System is the Control Plane," which was about removing kernel involvement for I/O operations, and "An Introduction to CHERI," which introduced the notion of capabilities, pointers carrying metadata to solve many memory mismanagement issues
  - Both of these reads were very interesting, and there are deeper, more in depth summaries in my Week4.md and Week6.md respectively
  - Since each paper went into topics (OS and C pointers) in a much deeper way than what I previously knew, there was a lot of learning done while reading. This made the two papers very beneficial in a way that it really expanded my knowledge on, for example, the nitty gritty of how OS work, and how we can improve latency by giving hardware direct access to I/O operations, or how pointers really work behind just writing `*p` in a C program, and all their weaknesses
- Created a File System in Rust
  - With the help of instructions, I fully implemented a file system in Rust, which was printable, had search functions, and read/write capabilities
  - Unlike the RPLB's projects, where it followed a tutorial style, this file system lab really helped with getting hands-on programming experience in Rust, personally, much more than both the RPLB projects combined
  - I used all the different topics we learned about in the past weeks (matching, structs, enums, lifetimes, ownership) to implement something real
  - The difficulty of the project felt a little unreasonable, due to it being the first actual coding project I was tasked with, but felt like at certain points I was completely lost, such as in step 3, with the implementation of taking in a Vector of strings, and converting it into a searchable path
- Downloaded Twizzler OS on my laptop
  - Followed the Twizzler OS download document to download Twizzler on my personal laptop
  - Created a Hello, World program in Twizzler
  - For the most part, I was blindly following the documentation's instructions, so how Twizzler OS actually works, and what it is doing is still very abstract to me
- Week-to-Week Engagement
  - My engagement with the course definitely fluctuated week-to-week, and was mostly due to whatever was structured for the given week. For example, weeks 4 and 6 were more engaging due to the paper readings we were assigned, as was week 7 due to the File System lab being due
  - Notably though, the last two weeks had very little engagement for me, due partly to the lack of attendance, and then also due to the lack of things to do. For example, in week 9, all that there was to do was to install Twizzler OS and run a quick Hello, World program

## Participation and Collaboration:
- Paper Discussions
  - I feel like I put serious effort into trying to understand both papers, so I could meaningfully contribute to the paper discussions. This effort made me much more comfortable and confident in these discussions and the topics in them (aforementioned OS and pointers)
  - However, the actual discussions themselves were quite awkward and lackluster
  - For the Arrakis paper, the initial scheduled discussion was postponed due to small attendance, and once the discussion finally took place, it didn't feel like a discussion but a way to show that each person did the reading so they wouldn't get in trouble
  - For the following CHERI paper, these same issues followed
- Lab Community
  - Initially, it didn't feel like a strong lab community, as it was my first time meeting everyone
  - As time went on though, I got more comfortable with all other labmates
  - With this being said, due to such fluctuating attendance, it was hard to create a strong community feeling, especially because most of the work was independent
  - The only real groupwork we did were the paper discussions, but as mentioned earlier, they didn't really achieve the goal that it was meant to (discussing ideas and questions -> trying to prove that each person did the reading)
- Personal Engagement Reflection
  - Going back, I would have definitely put more effort into engaging with the RPLB, as that was the main source of learning this class provided. However, I would mostly skim chapters, or feed them into AI and have it summarize the chapters for me. This led to an extremely fragile understanding of Rust concepts, and this showed during the first couple steps of the File System project, where I had to relearn how to use match statements, or lifetimes
  - Outside of the readings, I wished I had just done more personal practice using Rust, as a big issue for me was that even if I could properly regurgitate what I was reading in the RPLB, actually implementing a program from scratch was something very difficult for me
  - I also wish I had put in more effort with building relationships between myself and other labmates, or TAs. I felt that this was an aspect that I lost out on, as I can't really answer the "Were there moments where a conversation with a labmate or TA meaningfully changed how you thought about something?" question, as it is almost inapplicable, due to there not really being a relationship built for these conversations to arise

## What I Gained:
- What I Learned
  - After 10 weeks, I am proud to say that I am confident in programming basic software with Rust. Rust has been the hardest programming language I have learnt so far, with many new concepts that never even existed in previous languages I've worked with (lifetimes, ownership, matching), but after much reading and practice, I can properly understand the basics of the language. This being said, there are still a lot of things I am not as versed with, such as asynchronous programming, and still programming with Rust itself for harder, more complex software is something that I am still learning to do
  - I also learned how to properly read research papers, and understand the innovative ideas that are driving the publication. Starting with the Arrakis paper, grasping what was going on was extremely difficult, as I had little understanding of what an OS was outside of that it just abstractly connects hardware to software. However with the help of YouTube and Claude, I had a decent grasp over the paper, and I am proud of the summary/reflection of the paper I was able to write in Week4.md. Then for the CHERI paper, this one was much more easily digestible, but still significantly furthered my understanding of how pointers really worked behind the scenes
  - A moment a paper genuinely changed how I saw research was finally grasping the core idea behind the Arrakis paper. Previously, it was almost depressing how behind I was in my scope of knowledge, and it started unconsciously painting a negative image of frontier research for me, because I believed I wasn't smart enough. However, after many rereads and Claude prompts, when the Arrakis paper finally clicked, it was one of the most satisfying moments throughout Spring quarter. It gave me the confidence that I am able to understand frontier work
- Meeting the Goals of the Class
  - In all honesty, a lot of the goals set by the class fell short. While I am more confident in my Rust understanding, actually implementing code is still foreign due to the lack of structured coding assignments (my fault also for not practicing on my own)
  - Regarding the research contribution, at least for the first cohort, there was absolutely no research contribution done. This is likely due to the goal/difference between the first cohort and second, as the major goal of the first cohort is setting up students for Twizzler OS contributions as they move towards the second cohort. However, this aspect also falls short, as there was zero structure towards learning about Twizzler OS outside of mentions of it until week 9, where we downloaded the research OS
  - This being said, personally I feel like I am much more able to read innovative paper work in fields/topics I have very little background knowledge about, so in that sense, this class has fulfilled that goal
  - I want to carry forward the Rust basics I have built into future projects/subtasks in Twizzler, and I also want to carry forward all the mistakes and regrets I have during this quarter, such as weak relationships between labmates, and fix them going forward

## Feedback on Course Structure:
- What Worked
  - A large issue for me was that after reading chapters in the RPLB, I would forget them in the following days. The weekly notebook check-ins, where I would summarize what I learned helped reinforce and served as a memory jog of what I had read, which I found really helpful in really absorbing fully what I was learning. Also, the weekly git commit checks are a good way to ensure the notebooks are seen in a reflective purpose, and not a busy work assignment we must cram the night before the notebook checks happen
  - The paper selection I found was very relevant to the overall goal of the class (OS/Security Research), as both papers built upon my own knowledge in a way that benefited my understanding of OS/Security. I only wish that there were more paper readings (maybe one every other week), and the discussions were held more professionally and focused
  - I felt that the AI policy of "use it as a tool, not a crutch," was very helpful. It drew an effective line at using it in a beneficial way to supplement our learning, but not too far where it took away from our work
- What Didn't Work
  - The structure of learning Rust to me felt extremely inefficient. The large learning resources were the RPLB and Rustlings, but I really believe the best way to learn a language is just to build things in it. The Rustlings, in all honesty, were personally completely useless, and felt like a chore I had to get done before each Thursday section. The book was more helpful in the way it built my understanding of the language and its topics, but without actual structured implementation of the topics, I only gained theoretical understanding of Rust, and not practical skills
  - I think the File System lab was a great and efficient way to boost our understanding of Rust, but I just wish there were more lab projects. I feel it would be best to cut out Rustlings entirely, and replace it with weekly lab projects that stay in scope to what we are reading about in each book. This more difficult course load would also force people to take the class more seriously, instead of treating it as a resume boost. The issue I had with the File System lab is the difficulty level. I think the scope of difficulty was fair given that we were in week 6 and onwards, however since it was the first real thing we were building, it would have helped if we had progressive labs that get more difficult and involved as the course progresses, such as: Week 1: Hello, World program -> Week 2: Build a calculator -> … -> Week 6: Build a Filesystem
  - The three hour block also felt extremely stretched, and as if we were just there to be there. Most of the time, the lab time was spent doing independent work (readings or independent Rustlings), and since we were all at different points of the book/Rustling exercises, there was little collaboration being done. If there were more collaborative projects/things to do during the lab time instead of just reading the RPLB, the three hour block would feel much more fulfilling. And regarding the 6 hour in-lab time commitment, to be honest, there wasn't a single week where I spent 6 hours in the physical lab. However, each week I would spend upwards of 6 hours doing work relating to the class
  - Also, I feel like there should be more structure put into understanding Twizzler OS, as it is basically the whole goal of the first cohort: a learning stage to give students the knowledge to contribute to Twizzler OS
- Concrete Suggestion
  - I really believe that the best change to be made to the course structure would be weekly Rust programming assignments, that relate each week to what we are reading. This would pair the theoretical understanding given by the book, with applied practical skills through programming
