# Week 8 - [05/18/2026 - 05/24/2026]
## What I Did:
- Downloaded Twizzler OS on my laptop
  - Followed the instructions of the repo's BUILD.md
- Completed the Rust Programming Language Final Project: Multi-Threaded Web Server from chapter 21
  - Built a multi-threaded web server that accepts requests and distributes them across a fixed pool of worker threads
  - Set up a system where incoming requests get lined up and passed to whichever worker is free
  - Added a clean shutdown process so that when the server stops, every worker finishes its current task and closes properly
## Tasks Due Next Week:
- Familiarize myself with the Twizzler codebase, and create a "Hello World" program in Twizzler.
## Goals:
- Begin preparing to start contributing to the Twizzler codebase
- Use the "Hello World" program to get the chance to learn how Twizzler works
## Thoughts/Challenges for the Week (Reflection):
- Multi-Threaded Web Server
  - Due to the way the final project was set up, it was more of a tutorial on how to build a multi-threaded web server rather than an assignment of building one yourself.
  - Because of this, I found myself working backwards when trying to understand the project.
  - Instead of blueprinting how to build what, it was more of a process of looking at the given code solution and deciphering what everything meant.
  - While I got the general idea of what was being done and what each function did, the lower-level details were still lost to me.
  - To my abstract understanding:
    - The main function sets up the TCP, and in lib.rs, we have a thread pool which spawns a constant amount of workers.
    - Then, whenever a task is requested from the server-side, we use the execute function to give an available worker the request.
    - Through the handle_connection function in main.rs, the worker completes the request.
    - Then, when we are finished, we call drop from lib.rs to close down the web server and close down each worker once they are done with their current request.
  - I still lack the finer details of this program, such as how exactly each worker is given a task and how that is orchestrated.
  - I don't completely understand what a lot of the functions used do or what their purpose is.
  - This is my first exposure to thread handling, as my background consisted of basic C programming and mainly Python, but I am eager to continue learning and working with thread handling in Rust in the future.
- Downloading Twizzler OS
  - In the process of downloading Twizzler OS, there were some difficulties:
    - Initial download when I was pulling the toolchain took longer than expected, so I had to close my laptop to head to class, but once I reopened my laptop, I had found out that my pull had been cancelled
    - My next download attempt was at the Thursday Lab section, where after successfully pulling the toolchain, I came across issues with building, as some directory was empty, which caused failures while building
    - After resolving the build issues with the help of Surendra, I finally had Twizzler downloaded on my laptop
  - I am very excited to finally be able to start working on Twizzler OS, as that is what these last 9 weeks have been building up for
  - My initial thoughts of navigating the new OS were filled with a lot of confusion, as I didn't really understand what was going on, but I am certain with time and experience, I can familiarize myself with Twizzler.
