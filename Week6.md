# Week 6 - [05/4/2026 - 05/10/2026]

## What I Did:
- Completed Rustlings Exercises up to and including Threads (Rustlings 20)
  - Debugged different types of errors in topics like asynchronous programs and smart pointers
- Read The Rust Programming Language (Brown edition) up to and including chapter 17 (Fundamentals of Asynchronous Programming)
  - Learned about how to use smart pointers for dynamical memory allocation in the heap
  - Learned how to use the async keyword and threads to have functions run simultaneously during runtime
- Continued watching the YouTube Rust playlist "The Rust Lang Book" by Let's Get Rusty (up to video 30)
  - Supplemented my prior learning with coding examples in the videos
  - Went over smart pointers and concurrency with live examples of how each topic works in Rust
- Read through "An Introduction to CHERI" paper
  - Learned of the implementation of capabilities over pointers, and how this adds memory guardrails in C/C++
  - Downloading the paper on my iPad to take notes on the paper itself
  - Used Claude to simplify parts that I didn't understand, and help understanding throughout the paper
- Completed steps 1-4 of the Filesystem Lab Project
  - Implemented a recursive algorithm to print a tree of nodes, which were either files with their names or directories with their entries
  - Created a find function, that recurses through the tree and returns the specific file/directory, with proper error handling

## Tasks Due Next Week:
- Read chapters 18-19 in The Rust Programming Language (Brown edition), which teach of Object Oriented Programming and Patterns and Matching in Rust.
- First lab project, where we build a multi-backend filesystem

## Goals:
- Familiarize myself in OOP and Patterns and Matching in Rust
- Use the lab project to get even more hands on experience building from scratch in Rust

## Thoughts/Challenges for the Week (Reflection):
- The topics on smart pointers and especially asynchronous programming were very difficult to grasp
  - My previous programming experience was mainly Python, where I never needed to consider pointers
  - I never had touched asynchronous programming, so this introduction to it was very foreign
  - I don't really understand how to use threads and async, and what the differences are between them
  - Hoping after more hands-on exposure in async programming, I can understand the topic better
- "An Introduction to CHERI" felt much more digestible compared to "Arrakis: The Operating System is the Control Plane"
  - I had much of the previous needed background knowledge to understand the paper, as CSE 12 had covered a significant portion
  - Learning more of C/C++ pointers and their weaknesses helped solidify my understanding of how pointers work in Rust, and what the safety features actually help fix in Rust
  - I found the paper very convincing, and the technique of extending pointers to have metadata a strong solution to a long time problem of memory safety
- Regarding the first lab project initial thoughts (before starting)
  - I am very excited to begin really coding in Rust instead of just debugging in Rustlings
  - The Command Line Program we built in chapter 12 was extremely helpful, and I see this being the same case
- Regarding steps 1-4 of the lab project
  - Extremely difficult, and the project feels very uncomfortable since this was only the second real build from scratch assignment
  - Since I mostly didn't really practice anything I was reading about, so much felt unituitive
  - Things like matching or error handling, which I had grasped the week I had read about them, I completely forgot about and had to reteach myself how they worked
  - The compiler is very useful, and has helped me brute-force certain sections
  - Step 3, specifically the iterator function which connects the strings into a tree was extremely hard for me to implement
  - Got completely stuck on the function, and used Claude to give me direction, which I included in my Integrity.md
  - After the brutal first 3 steps, I am starting to get used to Rust, and step 4 felt much more comfortable as it was mostly just refactoring/using the topics that I worked on in the first few steps

## "An Introduction to CHERI" Summary:
CHERI (Capability Hardware Enhanced RISC Instructions) gives new safety guardrails around spatial and temporal memory safety in C/C++by altering the way we think of pointers through an extension of ISA. Instead of having pointers be an integer which addresses memory, which is hazardous if pointers behave in unexpected ways such as forging new pointers or going out of bounds, CHERI adds metadata attached to the pointers address which is then referred to as a capability. The metadata includes bounds, perms, otypes, and a tag validity bit. This in turn doubles the pointers bit width, i.e. 64 bit pointer -> 128 bit pointer + tag bit [1]. Going into each part:

Bounds: Gives an upper and lower bound on what memory the pointer can access.

Perms: Restricts the pointer to only certain types of instructions, like loads or saves.

OType: Gives the capability a state of sealed or unsealed. Usable if unsealed, or if sealed, it is not able to be dereferenced or mutated.

Tag validity: Stored separately from the capability bits, and tells hardware whether the set of bits (128 for 64 bit systems) is a valid capability or just garbage values.

Paired with this new metadata are three rules which each capability must follow. These rules ensure that a capability cannot be maliciously forged, adding to the security. Note that there are few exceptions, but this is the general overlay. The rules go as follows:

Provenance Validity: New capabilities can only be created by prior capabilities.

Capability Monotonicity: New capabilities bounds and perms are restricted to be a subset of the source capabilities.

Reachable capability monotonicity: In a given program, the overall perms and bounds cannot increase across the program.

The strengths of this approach to pointers are the aforementioned security benefits, but an additional strength of CHERI is scalable compartmentalization. In modern systems, compartmentalization is done by the MMU, where each compartment is given an address space. This is not scalable, as if you want a large number of compartments, each one needs its own address space, which causes IPC overhead. CHERI instead uses the capabilities bounds attribute to compartmentalize, ensuring isolation. Another strong suit of CHERI is that it is beyond just an idea, but it has real machine-checked theorems via Isabelle proofs, and is deployed through Sail as open source.

Weaknesses include the obvious increase in pointer bit size. This is especially harmful for pointer heavy tasks, such as language runtimes. Furthermore regarding the newly introduced metadata is the references of the tag bit. Since the tag bit isn't part of the actual capability in memory, it must be fetched. This causes bandwidth traffic that hurts performance. A solution was treating tag searching as a hierarchical scheme, which minimizes the issue, but doesn't absolve it. The last and seemingly largest weakness is the coordination issue with modern hardware and software. For CHERI to work, it needs not only an addition to ISA, but also a special CPU to hold all the new bits. This is financially infeasible, and is likely the reason deployment of CHERI has been limited. 

While the paper was extremely interesting and fairly digestible compared to the Arrakis introduction, I was still left with many questions. One was how the hierarchical scheme worked mechanically to optimally fetch bits. I understand that as memory is allocated, something tracks the density of valid tag bits, which prevent unnecessary searching, however the specifics are lost to me. Another question I had was regarding the two approaches of capability implementation. Pure capability, where every pointer becomes a capability, or the hybrid capabilities approach, where only certain pointers are turned into capabilities. This would keep the security benefits, as the most hazardous pointers would then be safe, while not taking up as much bit width. However does this mean that for prior C/C++ programs, like Linux, someone would have to go through the source code and manually change the needed pointers? If so, this would make CHERI very impractical to deploy. Also, while reading of the 3 rules of unforgeability, it seemed that rule 3 (reachable capability monotonicity) was redundant, as rule 2 (capability monotonicity) by definition covered what rule 3 was restricting.

References:
[1] R. N. M. Watson, S. W. Moore, P. Sewell, and P. G. Neumann, "An Introduction to CHERI," University of Cambridge, Computer Laboratory, Cambridge, UK, Tech. Rep. UCAM-CL-TR-941, Sep. 2019.
