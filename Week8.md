# Week 8 - [05/18/2026 - 05/24/2026]

## What I Did:
- Read chapter 20 of the Rust Programming Language Book (RPLB), Brown Edition, officially finishing it
  - Learned about unsafe programming, which give access to certain "unsafe" protocols like raw pointer access and hardware I/O
  - Learned of advanced traits, types, and functions, and how they are extra tools for shaping types and traits in ways that basic Rust can't, allowing for more flexible and reusable code
- Finished parts of the RPLB Final Project: Multi-Threaded Web Server (MTWS)
  - Set up a server that listens for web requests on a local port
  - Made it respond to different URLs with different HTML pages (including a 404 page for unknown routes)
  - Added a thread pool so the server can handle multiple requests at once instead of one at a time
  - Implemented a ThreadPool struct that creates a fixed number of worker threads when the server starts

## Tasks Due Next Week:
- Download the needed toolchain and dependencies to be able to run Twizzler OS on my personal device
- Complete the Final Project: Multi-Threaded Web Server from chapter 21 in the RPLB

## Goals:
- Begin preparing for real Twizzler OS work
- Reimplement and finish the MTWS project without looking at the source code to solidify how threads and concurrent programming work in Rust

## Thoughts/Challenges for the Week (Reflection):
- RPLB Chapter 20
  - Very confusing and dense chapter with a lot of new content covered
  - I wonder about the systems use cases for unsafe programming, specifically with Twizzler as a lot of what it opens up seems closely related with OS development, such as given access to raw pointers or hardware I/O
  - With advanced traits and types, it seems a lot of new possibilities open up, but again I wonder about the use cases
  - Unlike with lifetimes or ownership, which solve very practical and obvious issues, advanced traits and types seem a little extra
  - This is likely due to my inexperience with using them paired with my inexperience in the problems they are used to solve: catching mistakes and expressing things plain types can't
- Overall Thoughts on the RPLB
  - After finishing chapter 20, I am finally done with the entire book outside of the MTWS project
  - The book didn't feel really that helpful in learning Rust
  - A lot of the topics felt abstract even after multiple rereads, and due to the sheer volume of content we were reading each week, each chapter I read, I would forget the very next week
  - I believe this book would be much more effective if paired with weekly programming assignments based on the topics covered, as that would reinforce learning in a way were absorbing text from a book isn't able to
  - The practice problems we have started to do during the lab time have felt personally very effective at teaching Rust compared to pure reading alone
- Multi-Threaded Web Server
  - While I have not yet finished the project in its entirety, I don't believe the project to be the most useful for learning threading and concurrency in Rust
  - The way the project is set up is that its not really a project where you are given problems to solve yourself, but more like you are following a tutorial on building the web server
  - Unlike the FS lab, which gave us instructions to complete, the MTWS feels more like a really abstract demonstration on how to build the project, as solution code is fed to us
  - The solution code isn't given in a way where you would look at it if you were stuck, but literally as the book is explaining what to do
  - This poor project direction paired with my already lack of experience/knowledge in threading and web servers make it feel like I am just passively digesting whatever is being made, instead of really thinking about what is going on
  - The idea of a MTWS is really cool though, and I have been trying to understand the solution code handed out, but a lot of whats being done is via abstracted functions that basically do the work for you
  - To fix this, I will attempt to reimplement the project myself only reading the section headers and not relying on the obvious hints/solution code
