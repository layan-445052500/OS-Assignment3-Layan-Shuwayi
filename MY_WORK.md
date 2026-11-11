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
| **Full Name** | [Layan Ibrahim Shuwayi ليان ابراهيم شويعي] |
| **Student ID** | [445052500] |
| **University Email** | [445052500@std.psau.edu.sa |
| **GitHub Username** | [layan-445052500] |
| **Repository Link** | [https://github.com/layan-445052500/OS-Assignment1-Layan-Shuwayi] |
 
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

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [november 8, 2026 - 8:30 pm]
**What I did**: forked the original assignment 3 starter repository on github.

**Details**:
- renamed the repository using my first and last name.
- confirmed that the repository is public.
- updated the defualt ID with my actual ID.
- committed the student ID change to github.

**Challenges**: understanding the repository setup and identifying where to update the student ID.

**Solution**: followed the readme instructions and located  the student ID variable in the java source file.

**Time spent**: 30 minutes. 

---

### Entry 2 - [november 10, 2026 - 6:00 pm]
**What I did**: set up the development environment and tested the original program.

**Details**:compiled and ran the original jva program before implementing any synchronization features, saved the output in original_output.txt for comparison with final version. 

**Challenges**: identifying the synchronization proplems in the original program.

**Solution**: ran program and saved its output to use as a reference during development.

**Time spent**: 20 minutes.

---

### Entry 3 - [november 10, 2026 - 6:21 pm]
**What I did**: commited the ReadyQueue synchronization feature.

**Details**: added a ReentrantLock to protect the shared list and map in ReadyQueue and updated the add(), poll(), processOf(), and snapshot() methods to ensure thread safe access.

**Challenges**: preventing concurrent threads from accessing and modifying the queue at the same time.

**Solution**: used lock() with try- finally to ensure the lock is always released.

**Time spent**: 40 minutes.

---

### Entry 4 - [november 10, 2026 - 7:00 pm]
**What I did**:commited the SharedStats synchronization feature.

**Details**: added a ReentrantLock to protect the shared statistics counters and updated the three counter methods and their getters to ensure safe updates and reads.

**Challenges**: preventing race conditions when multiple CPU threads update shared statistics.

**Solution**: used one shared lock to protect all counter operations and maintain consistent values.

**Time spent**: 15 minutes.

---

### Entry 5 - [november 10, 2026 - 7:15 pm]
**What I did**: commited the counting semaphore feature.

**Details**: added a counting semaphore to readyQueue and updated cpuWorker to use acquire() instead of busy waiting and implemented a shutdown mechanism to wake up waiting CPUs after all processes are completed.

**Challenges**: ensuring that CPU threads wake up correctly and the program terminates without geeting stuck.

**Solution**: used semaphore permits and an AtomicBoolean to signal shutdown only once.

**Time spent**: 20 minutes.

---

### Entry 6 - [november 10, 2026 - 8:00 pm]
**What I did**: tested the final synchronization program.

**Details**: compiled and ran the final program five times to check the synchronization features and erify that the program terminates correctly.

**Challenges**: making sure the results remain cosistent across repeated executions .

**Solution**: repeated the tests and checked the final verification output including the busy wait polling count.

**Time spent**: 15 minutes.

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [4 hours]

**Most challenging part**: coordinating CPU threads and implementing the semaphore correctly.

**Most interesting learning**: how locks and semaphores prevent race conditions and busy waiting.

**What I would do differently next time**: start earlier and test each feature separetly.

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

[Race conditions happen when multiple threads access shared data at the same time. Critical sections need protection to prevent these problems. I used ReentrantLock with try-finally to ensure mutual exclusion and safely release the lock. The counting semaphore allows CPUs to wait for available processes without busy waiting. I was surprised that the original starter program failed some verification checks because of race conditions and busy waiting. After implementing synchronization, the program produced consistent results.]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*
[implementing the semaphore and CPU shutdown. I found it difficult to understand how many permits were needed. I also had to make sure all CPU threads stopped correctly. Another challenge was preventing the program from getting stuck. I solved this by using a shutdown signal to wake up the waiting CPUs. This part helped me understand thread coordination better.]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[I overcame the challenges by reading the README and reviewing the Java code. I worked on one feature at a time. I compiled the program after each small change to check for errors. I also ran the program several times to check the results. When I was confused, I asked for help and reviewed the instructions again. This step-by-step method helped me complete the assignment.]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[In banking, locks protect shared account balances during money transfers. In ticket booking systems, synchronization prevents two people from booking the same seat. In websites, locks protect shared data from being changed at the same time. A print queue can use a semaphore to control access to printers. These examples show how synchronization keeps shared resources safe and organized.]

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

[The original starter had race conditions because multiple CPUs accessed shared counters without proper protection. One incorrect value appeared in the original verification output. For example, CPU-1 and CPU-2 may both read a counter value of 12 before either updates it. CPU-1 writes 13, then CPU-2 also writes 13, so one increment is lost. This can happen on real machines because thread execution can overlap, and the bug is difficult to detect because it does not happen in every run.]

Verification block of the **original starter**:
```
[ [1m[31m? WATCHDOG: the simulation did not finish (30 s). A process was lost, or a CPU is blocked forever, or the 'completed' counter lost an update.[0m

[1m[92m??? VERIFICATION (expected values are computed from YOUR seed) ???[0m
  Context switches (quanta executed)     expected ??       observed ??       [31m? MISMATCH[0m
  Completed processes                    expected ??       observed ?        [31m? MISMATCH[0m
  Total service time (ms)                expected ?????    observed ?????    [31m? MISMATCH[0m
  Busy-waiting polls (must be 0)         expected ?        observed ???      [31m? MISMATCH[0m] ]
```

Verification block of **my final version**:
```
[Context switches (quanta executed)     expected ┘ت┘ج       observed ┘ت┘ج       ظ£¤
  Completed processes                    expected ┘ة┘ة       observed ┘ة┘ة       ظ£¤
  Total service time (ms)                expected ┘د┘خ┘خ┘خ┘ث    observed ┘د┘خ┘خ┘خ┘ث    ظ£¤
  Busy-waiting polls (must be 0)         expected ┘ب        observed ┘ب        ظ£¤
  ظ£¤ All shared values are consistent.] 
```

**Explanation of the timeline:**
[1. CPU-1 reads the counter value (12).
2. CPU-2 reads the same value (12).
3. CPU-1 writes 13.
4. CPU-2 writes 13.
5. The final value is 13 instead of 14, so one update is lost.]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[I protected the ReadyQueue list and map using a separate ReentrantLock. I also protected the three SharedStats counters and their getters using one shared ReentrantLock. Using one statistics lock makes the code simpler and protects all counter operations, but it can cause extra waiting between independent updates. The separate queue lock prevents queue operations from blocking statistics operations unnecessarily. The locks provide mutual exclusion, but the default ReentrantLock is not fair, so bounded waiting is not guaranteed.]

| Critical section (variable / method) | Lock used | Why it needs protection |
|ReadyQueue.add() |ReadyQueue lock|Protects list and map updates|
|ReadyQueue.poll() |ReadyQueue lock|Prevents simultaneous removal|
|ReadyQueue.processOf()|ReadyQueue lock|Protects map access|
|ReadyQueue.snapshot()|ReadyQueue lock|Prevents unsafe list and map reading|
|contextSwitchCount and its methods|statsLock|Prevents lost updates|
|completedProcessCount and its methods|statsLock|Prevents lost updates|
|totalServiceTime and its methods|statsLock|Prevents lost updates and inconsistent reads|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [...] | [...] | [...] |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[CPUs repeatedly checked the ready queue when it was empty, causing busy waiting and wasting CPU time. The semaphore value represents the number of available processes in the ready queue. Its initial value is zero because the queue starts empty, and after all initial processes are added, its value becomes numProcesses. In the final version, CPUs block using acquire() until a process becomes available. The last CPU releases totalCPUs permits to wake all waiting CPUs so they can exit; without this signal, some CPUs could remain blocked forever.]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
[Producer-Consumer problem. The main program and CPU workers produce queue entries, while CPU workers consume them.]

**Semaphores for a bounded queue (name and initial value)**:
[empty = K ,full = 0 ,mutex = 1]

**Deadlock scenario and prevention**:
[producer holds the mutex while waiting for an empty slot, preventing the consumer from accessing the queue. We prevent this by acquiring the semaphore before the mutex, breaking the hold-and-wait condition.]

## Summary

**Key concepts I understood through these questions:**
1. race conditions and matual exclusion
2. ReentrantLock and critical sections
3. counting semaphores and prducer consumer synchronization

**Concepts I need to study more:**
1. deadlock conditions and prevention
2. lock fairness and bounded waiting

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
