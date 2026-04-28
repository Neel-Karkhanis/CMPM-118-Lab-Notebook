# Week 4 - [04/18/2026 - 04/25/2026]

## What I Did:
- Completed Rustlings Excersises up to and including Error Handling (Rustlings 13)
  - Got hands-on experience about different collection types such as hashmaps, and got basic exposure error handling
- Read The Rust Programming Langauge (Brown edition) up to and including chapter 9 (Error Handling)
  - Learned about collection types and their usages, and different ways for a program to handle errors
- Finished "Rust Tutorial" playlist by Tech with Tim (Tutorials 1-9)
  - Visually followed along as different Rust topics were given coding examples
- Started a new YouTube Rust playlist "The Rust Lang Book" by Let's Get Rusty (up to video 9)
  - Supplemented my prior learning with coding examples in the videos
  - Each video corresponds generally to a specific chapter of the Official Rust Programming Language
- Read through "Arrakis: The Operating System is the Control Plane" paper
  - Watched through a couple introduction to operating system YouTube videos to teach myself the needed background knowledge to understand the paper
  - Used Claude to simplify parts that I didn't understand, or to fill gaps in my prior knowledge such as what NICs are, or what all the benchmark tests meant

## Tasks Due Next Week:
- Finish chapters 10-14 of the textbook, where chapter 12 guides building a Command Line Program (CLP) from scratch
- Complete Rustlings up to and including 18 Iterators
- Quickly reread "Arrakis: The Operating System is the Control Plane" for the group discussion of the paper on the coming Thursday (04/30)

## Goals:
- Continue to develop a working understanding of Rust fundamentals
- Use the CLP project to help familiarize myself with Rust syntax and basics in a way Rustlings isn't able to
- Fill all the fundamental knowledge gaps I have in operating systems, as while reading the "Arrakis" paper, I realized how much I don't know.

## Thoughts/Challenges for the Week:
- This week's lab meeting had a very small attendance (only 3 people from the 1st cohort were there)
  - Had to postpone the full group discussion of the "Arrakis" paper due to the small attendance
  - Even though there were less people, I personally feel like the small group actually helped fix the awkwardness between lab members
  - We had a very small scale discussion of the "Arrakis" paper, but it still was interesting to see what different things everyone took away from the paper
- The lack of building a Rust project from scratch has made the language feel still unfamiliar, despite the textbook readings, YouTube videos, and Rustlings activities
  - This upcoming CLP project hopefully will give me real experience on building a Rust project from zero
- Starting to finally understand how memory really works, and how Rust has many guardrails that prevent mismanagement of memory

## "Arrakis: The Operating System is the Control Plane" Summary:
The Arrakis Operating System takes a new approach to handling I/O operations. Instead of having the kernel mediate every single operation, Arrakis splits I/O operations into two planes: control plane and data plane. The control plane is still done by the kernel, setting up and configuring I/O. What’s novel compared to modern adopted OS like Linux, is that the data plane is relinquished from the kernel’s responsibility, and is done through each application being given a VNIC (virtual network interface card) so each operation from the app can talk directly to the hardware without the kernel acting as a middle man. This shows “improvements of 2-5x in latency and 9x in throughput" [1].

The strengths of this approach are the aforementioned benchmark increases, but also the fact that Arrakis has two types: /N and /P. Arrakis/N is the native type, which requires special hardware support for virtualization, but Arrakis/P can be used with unmodified apps and unoptimized hardware. This means that Arrakis can work in the same conditions as Linux without modification, and still outperform. The only caveat is that Arrakis/P performs slightly worse than its native counterpart, and that it needs at least one extra core dedicated to VSIC emulation to show strong performance over Linux when hardware lacks virtualization. Arrakis is also able to keep file name lookups even though there is no kernel intervention in the data plane, as “Arrakis provides applications direct control over VSA storage allocation” [1]. This means it allows other applications to access each other’s data, filling up a hole of a lack of kernel mediation.
This being said, there are severe limitations which prevent Arrakis’ wide adoption. Since there is no kernel mediation as I/O operations talk to the hardware means that nothing stops malicious applications from hogging bandwidth. Although in the control plane, a rate-limit is set, this rate-limit isn’t dynamic, so during network contention this becomes a major issue as certain apps can monopolize bandwidth, affecting other applications’ performance.

After reading this paper, questions regarding some of the benchmarks arose. In Figure 4, the graph shows that as Processing time increases, both types of Arrakis and Linux all converge to the same throughput [1]. I wonder why this is, and what that means for Arrakis’ highly regarded performance benefits over Linux when it comes to larger activities like data inquiry. Another question I had was a large limitation was hardware without SR-IOV or with limited filter support, however this paper was written in 2015. I’m sure as over a decade has passed, these hardware limitations have been lifted, so what else could be preventing new research into Arrakis?

References
[1] S. Peter et al., "Arrakis: The Operating System is the Control Plane," ACM Transactions on Computer Systems, vol. 33, no. 4, article 11, Nov. 2015.


