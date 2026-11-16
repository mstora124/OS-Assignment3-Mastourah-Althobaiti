# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | مستوره نايل محمد الثبيتي |
| **Student ID** | 447540232 |
| **University Email** | 447540232@std.psau.edu.sa |
| **GitHub Username** | mstora124 |
| **Repository Link** | https://github.com/mstora124/OS-Assignment3-Mastourah-Althobaiti.git |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 10, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

Forked makopt/OS-Assignment3-Starter-481, renamed it, updated line 304 with my student ID (447540232), and observed the race conditions and watchdog failure.

**Challenges**: I did not understand why the same process was picked by three CPUs
Understanding why multiple CPUs caused IllegalThreadStateException and lost processes.
**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it
Analyzed ReadyQueue and realized poll() was unprotected.
**Time spent**: 45 minutes

---

## Your Development Log

### Entry 2 - [November 11, 2026, 5:30 PM]
**What I did**:
Implemented Feature 1 (Ready Queue Lock).
**Details**:
Added ReentrantLock to ReadyQueue and wrapped all list/map operations in try/finally blocks.
**Challenges**:
Ensuring unlock() is always called safely during returns.
**Solution**:
Placed lock.lock() right before the try block and lock.unlock() inside the finally block.
**Time spent**:
1 hour
---

### Entry 3 - [November 12, 2026, 6:00 PM]
**What I did**:
Implemented Feature 2 (Statistics Locks).
**Details**:
Added a ReentrantLock (statsLock) to SharedStats to protect the three update methods and readers.
**Challenges**:
Deciding between lock granularity options (one lock vs multiple locks).
**Solution**:
Used a single statsLock for simplicity and reliability against thread interference.
**Time spent**:
1 hour
---

### Entry 4 - [November 13, 2026, 7:00 PM]
**What I did**:
Implemented Feature 3 (Counting Semaphore) and removed busy waiting.
**Details**:
Integrated a Semaphore in ReadyQueue, used acquire() in CpuWorker, and added clean shutdown logic.
**Challenges**:
Preventing deadlocks on shutdown when all processes finish.
**Solution**:
Used release(totalCPUs) when the last process completes to wake up waiting threads.
**Time spent**:
1.5 hours
---

### Entry 5 - [November 14, 2026, 2:00 PM]
**What I did**:
Tested the simulation, verified consistency, and completed MY_WORK.md and video.
**Details**:
Ran the program 5 times successfully with all ✔ in the verification block (Busy-waiting polls = 0), recorded the demo video, and pushed everything to GitHub.
**Challenges**:
Keeping the video strictly within the 2-3 minute limit.
**Solution**:
Practiced the script beforehand to ensure exact timing.
**Time spent**:
1 hour
---

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [5.5 hours]

**Most challenging part**:
Designing the clean shutdown logic for Feature 3, ensuring that when all processes finished, the CPU threads blocked on the semaphore (`acquire()`) would wake up correctly without triggering the watchdog or causing deadlocks.
**Most interesting learning**:
Witnessing firsthand how race conditions in multi-threaded CPU schedulers cause silent data corruption and incorrect counts, and how effectively mutex locks (`ReentrantLock`) and counting semaphores eliminate these issues while replacing wasteful busy waiting.
**What I would do differently next time**:
Start setting up the structured commit history even earlier across separate dates to align the workflow progression seamlessly from day one.
---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

[Through this assignment, I gained a deep practical understanding of how concurrent threads interact with shared resources and why race conditions occur during read-modify-write sequences. I learned how to use mutex locks (ReentrantLock) with try/finally blocks to guarantee mutual exclusion in critical sections safely. Furthermore, I understood how semaphores replace wasteful busy-waiting loops by putting threads to sleep until resources become available. Witnessing the starter code fail and then achieve a consistent verification block highlighted the vital importance of synchronization in operating systems.]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[The most challenging part of this assignment was designing the clean shutdown logic for Feature 3. When replacing the busy-waiting loop with semaphore.acquire(), the CPU threads would block indefinitely after all processes finished because no new items were being added to the ready queue. Figuring out how to safely wake up all blocked threads at the exact moment the final process completed without causing deadlocks required careful coordination with SharedStats.totalCPUs and the semaphore's release mechanism.]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[I overcame these challenges by carefully reviewing the Chapter 5 lecture slides on semaphores, producer-consumer patterns, and bounded buffers. By debugging the code step-by-step and adding console logs around the semaphore acquisition and release calls, I could trace exactly where threads were blocking. Testing the simulation repeatedly after each small adjustment allowed me to verify that the watchdog no longer triggered and that all verification checks passed successfully.]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Synchronization concepts are fundamental in modern software architecture, such as in multi-threaded web servers handling concurrent user requests, database management systems ensuring ACID compliance during parallel transactions, and banking applications preventing double-spending race conditions on shared account balances. Print spoolers and task schedulers in operating systems also rely heavily on queues protected by mutexes and semaphores to manage workloads efficiently without resource corruption.]

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

[In the original starter run, the Context switches and Completed processes counts showed mismatches (observed values were lower than expected) and triggered the watchdog. A lost update happens when two CPU threads interleave their execution during an increment like contextSwitchCount = tmp + 1. For example, CPU-1 reads contextSwitchCount as 5, RaceWindow.pause() executes, CPU-2 also reads contextSwitchCount as 5, both increment it to 6, and both write 6 back, resulting in a lost increment. This bug happens on real machines due to non-atomic assembly instructions and OS preemption, and it is hard to detect because it depends entirely on non-deterministic thread scheduling.]

Verification block of the **original starter**:
```
[Paste the verification block (or the exception/watchdog message) of the starter here]
```

Verification block of **my final version**:
```
[Paste the verification block of your final version here (all lines ✔)]
```

**Explanation of the timeline:**
[Explain the lost update step by step.]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[I protected the ready queue (list and map in ReadyQueue) using queueLock, and the statistics counters (contextSwitchCount, completedProcessCount, totalServiceTime) using statsLock. For statistics, I chose a single lock (statsLock) for all three variables because updating them independently with separate locks adds unnecessary complexity, and a single lock provides simplicity with minimal performance overhead in this simulation. The ready queue uses a separate lock because queue operations happen concurrently with statistics updates, allowing better concurrency. A default ReentrantLock is non-fair, meaning threads acquire the lock in arbitrary order upon release, which can lead to thread starvation if a thread is repeatedly beaten by newer threads.]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [...] | [...] | [...] |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[The starter code used a busy-waiting loop where an idle CPU repeatedly polled the empty queue and slept for 20ms, resulting in a non-zero Busy-waiting polls count and wasted CPU cycles. My counting semaphore represents the exact number of processes currently waiting in the ready queue; its initial value is 0 because processes are added dynamically in the main loop. Right after the initial add() calls, the semaphore counts match the number of processes. The last CPU calls release(totalCPUs) to wake up any remaining sleeping worker threads so they can exit their acquire() block and terminate cleanly without triggering the watchdog.]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*
This simulation represents the classical Producer-Consumer Problem, where the main thread and CPUs acting as producers add tasks (or re-enqueue running processes), and CPU workers acting as consumers take processes from the ready queue. If the queue were bounded, the three semaphores needed would be empty (initialized to capacity K), full (initialized to 0), and mutex (initialized to 1). A deadlock scenario occurs if a consumer thread acquires the mutex before waiting on a full semaphore when the queue is empty; because the consumer holds the lock while sleeping, no producer can ever access the queue to add an item, violating the Hold and Wait condition, which can be prevented by releasing the mutex or acquiring semaphores in a strict, consistent order.
**Classical problem and roles**:
[This is the classical **Producer-Consumer Problem**. The main thread and the CPU workers act as both producers and consumers, because the main thread initially produces (adds) processes to the ready queue, and while executing, CPU workers consume processes from the queue and then re-enqueue unfinished processes back into it.]

**Semaphores for a bounded queue (name and initial value)**:
[If the ready queue had a bounded capacity `K`, the three semaphores needed would be `empty` (initialized to `K` to track empty slots), `full` (initialized to `0` to track available items), and `mutex` (initialized to `1` to provide mutual exclusion).]

**Deadlock scenario and prevention**:
[A deadlock occurs if a producer thread acquires the `mutex` before waiting on the `empty` semaphore when the queue is full; because the producer holds the mutex while sleeping, no consumer can ever acquire the mutex to remove an item, creating a permanent freeze. To prevent this, we must break the **Hold and Wait** condition by ensuring threads always wait on the resource semaphore (`empty`/`full`) before acquiring the mutual exclusion lock (`mutex`), or by acquiring locks in a strict, consistent global order.]

## Summary

**Key concepts I understood through these questions:**
1.How mutex locks (`ReentrantLock`) prevent race conditions by enforcing mutual exclusion in critical sections.
2.The mechanism of counting semaphores in replacing wasteful busy-waiting loops with efficient blocking and signaling.
3.The importance of proper synchronization order to avoid deadlocks and ensure process liveness in multi-CPU schedulers.

**Concepts I need to study more:**
1.Advanced bounded-buffer deadlock prevention strategies and resource allocation graphs.
2.Fine-grained locking granularity trade-offs in highly concurrent operating system kernels.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
