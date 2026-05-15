# Week 7 - [05/12/2026 - 05/19/2026]

## What I Did:
- Read chapters 18 and 19 of the Rust Programming Language Book (RPLB), Brown Edition
  - Learned about what object-oriented programming looks like in Rust, and its limitations
  - Went into a further deep dive of pattern matching and how it works systematically
- Finished the filesystem lab
  - Implemented a display function to print out the tree
  - Implemented a find function to navigate through the path of the tree in order to find a target directory/file
  - Created handles for directories/files to be able to read/write to them
  - All implemented with proper error handling throughout
  - Used the collective knowledge learned from all the previous RPLB chapters + YouTube videos
  - Debugged until the program passed the given tests

## Tasks Due Next Week:
- Read the final chapter of the RPLB on advancing topics previously taught
- Complete the Final Project: Multi-Threaded Web Server from chapter 21 in the RPLB

## Goals:
- Begin developing a more advanced understanding of the basics of Rust
- Use the Multi-Threaded Web Server project to develop skills using threads, as previously that was a weakness
- Learn how networking works between client and hosts, and how messages are relayed

## Thoughts/Challenges for the Week (Reflection):
- RPLB Chapters 18 - 19
  - It was interesting to learn about what OOP features Rust has, but it was unfortunate that there is no implementation inheritance
  - We use structs and impl blocks along with composition to mimic OOP, but given the lack of implementation inheritance, OOP in Rust looks different than in languages like Java or C++
  - Pattern matching was always something that confused me, even though it was introduced so early in the book, however chapter 19 made it even worse
  - Learned how if let/while let, match, and let else work systematically, but this really just further made me uncertain of the use cases of pattern matching
  - Getting hands on practice using match statements various times throughout the fs lab did help in my abstract understanding of them though
- FileSystem Lab (Overall Thoughts)
  - This lab felt extremely uncomfortable for me
  - A large issue I have had with learning Rust is the pace, one week I would learn 3 different topics a normal CS class would cover in 3 separate weeks. For example, in 13s, we've been spending the last week and half talking about structs, but here we went over structs in one week in addition to two other topics.
  - This made my understanding of each topic extremely thin, and even if I would grasp the concept the week of reading of it, once I move on to the next few topics, I would forget about what I learned about the week prior
  - This was largely due to the lack of real practice with Rust, as most of the learning was just reading and trying to internalize how Rust worked
  - It may be more beneficial in the future to ramp up project difficulties as weeks go on in CMPM 118 like it is done in 13s, or other programming classes
  - That being said, the strongest reason why the project felt uncomfortable was my half-ass effort in learning, as I would read a chapter for the sake of reading it, instead of trying to really understand whats being said
  - The sudden drop into what to me was a very intermediate project, at least compared to debugging small Rustling activities, made the lab very difficult to complete
  - Since the lab used elements throughout the book, most of which I had forgotten, a large chunk of time was going back to remember what lifetimes were for example
  - Once I had caught myself back up to speed though, the lab itself was very interesting to work on
  - As said before, it incorporated almost every topic we learned before, so it felt like a culmination of everything we had been learning for the past 6-7 weeks.
  - Completing it took 7+ hours in all, but it has made me much more confident in Rust programming
  - After finishing, I now feel solid on using lifetimes in practice, working with recursive enums, and navigating nested data structures with match.
- FileSystem Lab (Specific Troubles) 
  - Obstacle 1: Building the initial print function using recursion felt understandable, but transitioning that into the fmt::Display method was something I didn't really understand. I understood what the method was trying to do (enabling println!("{}", fs);) but the actual syntax of fn fmt<'a>(&self, f: &mut fmt::Formatter<'a>) -> fmt::Result still doesn't quite make sense to me on what everything is in the signature is doing/what it means.
  - Obstacle 2: Moving past the Display method, which wasn't that hard to implement, but more so an understanding block, the real implementation block was turning an iterator into a Path. After the lab session on Thursday, where Surendra went over the solution code and what everything meant, I now semi-understand what the solution was doing (placing the generic iterator into a reversed vector, and using fold to push the elements of the vector into a Path), which was very helpful.
  - Obstacle 3: After getting past the FromIter hurdle, a lot of the rest of the lab was reusing topics that the first 3 steps had went over, so it was much smoother than the initial curve of having to reteach myself a lot of what was needed. However, after finishing lib.rs and completing all the steps, and running cargo test, the terminal exploded with errors. I didn't know what was going on, so I ended up just plugging the errors into Claude along with my codebase, where it told me that my signatures weren't matching the test cases. That lead to the obstacle of having to refactor much of my structs/impl blocks to follow the tests, such as changing certain structs into tuple structs. But finally after much changing and debugging, I got a working Filesystem that passed all tests.
- A note on AI usage
  - I knew that my Rust programming skills were extremely lack luster, so I went into this project wanting to build up those skills.
  - However, with every obstacle I didn't really know how to fix it on my own, and am disappointed with the amount that I relied on AI, where it be helping with debugging or explaining topics I should have known
  - I have documented the majority of my AI usage through sharing my Claude chats in the Integrity.md, however some parts were left out as it involved help from AI in a chat regarding other things, such as other coursework assistance or personal things, which I did not include into the Integrity.md, only the purely fs lab focused chats for privacy.
