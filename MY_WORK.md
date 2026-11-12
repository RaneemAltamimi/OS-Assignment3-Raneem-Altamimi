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
| **Full Name** | [Write your full name here] |
| **Student ID** | [Write your student ID here] |
| **University Email** | [yourid]@std.psau.edu.sa |
| **GitHub Username** | [your-github-username] |
| **Repository Link** | [Paste your repository link here] |
 
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

**## Example Entry (do not copy it, write your own)**

**### Entry 1 - [November 2, 2026, 4:30 PM]**
**\*\*What I did\*\***: Forked the repository, set my student ID, and ran the original starter

**\*\*Details\*\***:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**\*\*Challenges\*\***: I did not understand why the same process was picked by three CPUs

**\*\*Solution\*\***: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**\*\*Time spent\*\***: 45 minutes

**---**

**## Your Development Log**

**### Entry 1 - [November 12, 2026, Enter actual time]**

**\*\*What I did\*\***: Reviewed the assignment instructions and studied the original Java code.

**\*\*Details\*\***:
- Read the Assignment 3 requirements and the README.md file.
- Reviewed the main classes in `SchedulerSimulationSync.java`.
- Identified the shared ReadyQueue and SharedStats variables.
- Studied how multiple CPU threads access the same queue.
- Identified the three synchronization features required by the assignment.

**\*\*Challenges\*\***: Understanding how multiple CPU threads interact with the same shared data and why synchronization is necessary.

**\*\*Solution\*\***: Followed the program flow between `ReadyQueue`, `CpuWorker`, `Process`, and `SharedStats` to understand how processes are added, removed, executed, and completed.

**\*\*Time spent\*\***: [Enter actual time spent]

**---**

**### Entry 2 - [November 12, 2026, 11:00]**

**\*\*What I did\*\***: Ran the original starter program and investigated the race condition in the ready queue.

**\*\*Details\*\***:
- Used student ID `445052093`.
- The program generated 13 processes, a time quantum of 4000 ms, and 2 CPUs.
- Observed that CPU-1 and CPU-2 both picked process P1.
- The output showed `IllegalThreadStateException` when the same thread was started again.
- Saved the original output for comparison with the final implementation.

**\*\*Challenges\*\***: Understanding why two CPUs could select the same process from a shared FIFO queue.

**\*\*Solution\*\***: Examined `ReadyQueue.poll()` and identified that accessing the first element and removing it were not protected by a lock. This showed the need to protect the complete queue operation as one critical section.

**\*\*Time spent\*\***: [Enter actual time spent]

**---**

**### Entry 3 - [November 12, 2026,12:00]**

**\*\*What I did\*\***: Repeated the original starter execution and investigated another synchronization failure.

**\*\*Details\*\***:
- Ran the original program again with the same student ID.
- Observed `NullPointerException` inside `ReadyQueue.snapshot()`.
- The verification output showed 25 expected context switches but 0 observed.
- The expected number of completed processes was 13, while the observed value was 0.
- The expected service time was 71819 ms, while the observed value was 0.
- Identified that the CPU threads terminated before executing the processes.

**\*\*Challenges\*\***: Understanding why iterating through the shared LinkedList could cause an exception while other threads were accessing it.

**\*\*Solution\*\***: Identified that `snapshot()` also needs synchronization because reading and iterating over a shared collection while another thread modifies it can cause concurrency problems.

**\*\*Time spent\*\***: [Enter actual time spent]

**---**

**### Entry 4 - [November 13, 2026, 1:00]**

**\*\*What I did\*\***: Implemented the mutex locks for the ready queue and shared statistics.

**\*\*Details\*\***:
- Added the `ReentrantLock` import.
- Declared `queueLock` inside the `ReadyQueue` class.
- Protected `add()`, `poll()`, `processOf()`, and `snapshot()`.
- Created separate locks for `contextSwitchCount`, `completedProcessCount`, and `totalServiceTime`.
- Protected the three update methods and the three getter methods.
- Used `try/finally` to guarantee that the locks are released.

**\*\*Challenges\*\***: Choosing the appropriate lock granularity and making sure that both reading and writing operations were protected.

**\*\*Solution\*\***: Used one lock for the ready queue and one separate lock for each independent statistics variable. This allows different statistics to be accessed concurrently without using one common statistics lock.

**\*\*Time spent\*\***: [Enter actual time spent]

**---**

**### Entry 5 - [November 13, 2026, 1:30 ]**

**\*\*What I did\*\***: Implemented the counting semaphore and worked on the clean shutdown of CPU threads.

**\*\*Details\*\***:
- Imported `java.util.concurrent.Semaphore`.
- Declared a counting semaphore with an initial value of zero.
- Added `release()` when a process is inserted into the ready queue.
- Replaced the polling loop with `acquire()`.
- Removed the `Thread.sleep(20)` busy-waiting section.
- Added a shutdown signal to wake up CPUs after all processes have completed.
- Planned to test the final implementation at least five times.

**\*\*Challenges\*\***: Making sure that CPUs do not remain blocked after the last process finishes.

**\*\*Solution\*\***: Used `release(totalCPUs)` to wake up waiting CPUs and checked the completed process count after acquiring a semaphore permit.

**\*\*Time spent\*\***: [Enter actual time spent]

**---**

**### Entry 6 - [Optional - Date and Time]**

**\*\*What I did\*\***: Completed the documentation and prepared the final demonstration.

**\*\*Details\*\***:
- Reviewed the implementation of the three synchronization features.
- Completed the Development Log, Reflection, and Technical Answers sections.
- Compared the original starter output with the final implementation output.
- Prepared the program execution in the IDE.
- Reviewed the commit history and prepared the video demonstration.

**\*\*Challenges\*\***: Explaining the synchronization concepts clearly and making sure that the written answers matched the actual implementation.

**\*\*Solution\*\***: Reviewed the Java code and verification results and connected each synchronization concept to the corresponding part of the implementation.

**\*\*Time spent\*\***: [Enter actual time spent]

**---**

## Development Log Summary

**\*\*Total time spent on assignment\*\***: [Add your actual session durations]

**\*\*Most challenging part\*\***: The most challenging part was understanding how multiple CPU threads could access the same ready queue at the same time. The original program sometimes allowed two CPUs to select the same process, which caused an `IllegalThreadStateException`. Understanding the semaphore shutdown was also challenging because all CPU threads needed to terminate correctly after the last process finished.

**\*\*Most interesting learning\*\***: The most interesting learning was understanding how a counting semaphore can replace busy waiting. I learned that a CPU can block when no process is available instead of continuously checking the ready queue.

**\*\*What I would do differently next time\*\***: I would start by studying the shared data and identifying all critical sections before changing the code. I would also test each feature separately and keep a record of the output after every change.

**---**

# Part B: Reflection (0.5 mark)

## Question 1: What did you learn about synchronization?

**\*\*Your Answer:\*\***

I learned that synchronization is necessary when multiple threads access and modify shared data at the same time. A race condition can happen when two threads perform a read-modify-write operation on the same variable, causing one update to be lost. I also learned that a critical section must be protected using mutual exclusion, which can be implemented with `ReentrantLock` in Java. The `try/finally` structure is important because it guarantees that the lock is released even if an exception occurs. Another important concept I learned was the counting semaphore, which allows CPU threads to wait until processes become available instead of using busy waiting. The original output helped me understand that concurrency problems can cause duplicate process execution and exceptions. Overall, I understood that synchronization is not only about protecting variables but also about coordinating the execution of multiple threads.

## Question 2: What was the most challenging part of this assignment?

**\*\*Your Answer:\*\***

The most challenging part of this assignment was implementing the counting semaphore with a correct shutdown mechanism. I understood that `acquire()` makes a CPU wait when there are no available processes, but this creates another problem when all processes have finished. Some CPU threads might still be blocked even though no more processes will be added to the queue. I had to understand how the semaphore count represents the number of available processes and why its initial value must be zero. Another challenge was making sure that the shutdown signal wakes up all waiting CPUs without making them try to execute a nonexistent process. This part required understanding the relationship between the ready queue, the semaphore, and the completed process counter. It helped me understand that thread synchronization also requires managing the termination of threads correctly.

## Question 3: How did you overcome the challenges you faced?

**\*\*Your Answer:\*\***

I approached the assignment by dividing the implementation into three separate features instead of changing everything at once. First, I studied the original code and examined the output to understand where the race conditions occurred. I then reviewed the synchronization concepts and the Java documentation to understand how `ReentrantLock` and `Semaphore` work. I focused on protecting the ready queue before working on the shared statistics because the queue problems affected the execution of the CPU threads. After that, I worked on the semaphore and examined how `release()` and `acquire()` coordinate the producers and consumers. Testing each feature separately helped me identify problems more easily and understand the purpose of every modification.

## Question 4: Where can synchronization concepts be applied in real-world applications?

**\*\*Your Answer:\*\***

Synchronization is important in many real-world applications where multiple users or processes access shared resources. In banking systems, locks can protect account balances during money transfers to prevent incorrect updates. In online ticket booking systems, synchronization can prevent two customers from reserving the same seat at the same time. A database can use locks to protect shared records while transactions are being processed. A printing system can use a queue and a semaphore to coordinate multiple users who send documents to a shared printer. These examples are similar to this assignment because they require controlled access to shared resources. Therefore, synchronization helps maintain data consistency and prevents unexpected behavior in concurrent systems.

**### Optional: What would you like to learn more about?**

I would like to learn more about deadlocks, starvation, and different synchronization algorithms. I am also interested in understanding how operating systems coordinate multiple processes and threads in real applications.

**### Optional: How confident do you feel about synchronization concepts now?**

Intermediate. I understand the basic idea of race conditions, critical sections, mutex locks, and counting semaphores. However, I still need more practice with complex deadlock situations and synchronization between multiple threads.

**### Optional: Feedback on the assignment**

The assignment was useful because it demonstrated how concurrency problems can affect a real program. Running the original code helped me understand why synchronization is necessary. The practical implementation also helped connect the theoretical concepts to Java programming. The shutdown mechanism was particularly useful for understanding how threads should terminate safely.

**---**

# Part C: Technical Answers (0.5 mark)

## Question 1: Race Condition in Your Own Output

**\*\*Your Answer:\*\***

In my original starter output, CPU-1 and CPU-2 both selected P1, which caused an `IllegalThreadStateException` when the same thread was started again. In another execution, both CPU threads encountered a `NullPointerException` inside `ReadyQueue.snapshot()`, and the observed context switches, completed processes, and total service time were all zero instead of their expected values. This happened because the original ready queue was not protected against concurrent access. A similar lost update can occur in `SharedStats` when two threads read the same counter value and then overwrite each other's updates. On a real machine, the same problem can happen without `RaceWindow.pause()` because thread scheduling can interrupt a read-modify-write operation at an unpredictable time.

**Verification block of the original starter:**

```text
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 25       observed 0        MISMATCH
  Completed processes                    expected 13       observed 0        MISMATCH
  Total service time (ms)                expected 71819    observed 0        MISMATCH
  Busy-waiting polls (must be 0)         expected 0        observed 0
  At least one check failed: a race condition or busy waiting is still present.
```

**Additional evidence from another original starter run:**

```text
[CPU-2] picks P1
[CPU-1] picks P1

Exception in thread "CPU-1" java.lang.IllegalThreadStateException
at CpuWorker.run(SchedulerSimulationSync.java:283)
```

**Verification block of my final version:**

```text
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 25       observed [COPY ACTUAL RESULT]
  Completed processes                    expected 13       observed [COPY ACTUAL RESULT]
  Total service time (ms)                expected 71819    observed [COPY ACTUAL RESULT]
  Busy-waiting polls (must be 0)         expected 0        observed [COPY ACTUAL RESULT]
  [COPY THE ACTUAL FINAL VERIFICATION MESSAGE]
```

**\*\*Explanation of the timeline:\*\***

For example, suppose `contextSwitchCount` is initially 12. CPU-1 reads the value 12, and then `RaceWindow.pause()` creates an opportunity for another thread to execute. CPU-2 also reads 12 before CPU-1 writes its result. CPU-1 writes 13, and CPU-2 then writes 13 as well, so one increment is lost and the final value is 13 instead of 14. The lock prevents this interleaving by allowing only one thread at a time to execute the protected update.

## Question 2: Critical Sections and Lock Granularity

**\*\*Your Answer:\*\***

I protected the ready queue using a separate `ReentrantLock` called `queueLock`. I also used three separate locks for `contextSwitchCount`, `completedProcessCount`, and `totalServiceTime` because these statistics are independent of each other. This design improves concurrency because updating one statistic does not block an update to another statistic. The ready queue needs a different lock because it protects a different shared data structure containing the linked list and the process map. Mutual exclusion is provided because only one thread can enter a critical section protected by the same lock at a time. The default `ReentrantLock` is not fair, so it does not guarantee bounded waiting and a thread could theoretically wait longer than another thread.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| `ReadyQueue.add()` | `queueLock` | Protects adding a thread to the list and its process to the map. |
| `ReadyQueue.poll()` | `queueLock` | Prevents two CPUs from removing the same queue element. |
| `ReadyQueue.processOf()` | `queueLock` | Protects access to the shared process map. |
| `ReadyQueue.snapshot()` | `queueLock` | Protects iteration over the shared list and map. |
| `incrementContextSwitch()` | `contextSwitchLock` | Prevents lost updates to the context switch counter. |
| `getContextSwitchCount()` | `contextSwitchLock` | Protects reading the context switch counter. |
| `incrementCompletedProcess()` | `completedProcessLock` | Prevents lost updates to the completed process counter. |
| `getCompletedProcessCount()` | `completedProcessLock` | Protects reading the completed process counter. |
| `addServiceTime()` | `serviceTimeLock` | Prevents lost updates to the total service time. |
| `getTotalServiceTime()` | `serviceTimeLock` | Protects reading the total service time. |

## Question 3: Busy Waiting vs Semaphore

**\*\*Your Answer:\*\***

In the original starter, a CPU repeatedly checked the ready queue and used `Thread.sleep(20)` when the queue was empty, which is an example of busy waiting. This approach wastes CPU resources because the CPU keeps checking for available work instead of blocking until a process arrives. My counting semaphore represents the number of processes currently available in the ready queue, and its initial value is zero because the queue initially has no processes. After the 13 initial `add()` calls, the semaphore value becomes 13 because each inserted process releases one permit. When the last process completes, `release(totalCPUs)` wakes up the waiting CPU threads so that they can terminate instead of remaining blocked forever. In my captured original starter run, the busy-waiting polls value was 0 because the CPU threads encountered exceptions before reaching repeated empty-queue polling.

## Question 4: Classical Problems and Deadlock

**\*\*Your Answer:\*\***

The synchronization problem represented by this program is the Producer-Consumer problem, where processes are inserted into a shared ready queue and consumed by CPU threads. The main thread acts as a producer when it initially adds processes, while CPU workers act as consumers when they remove processes from the queue. CPU workers can also act as producers when they put unfinished processes back into the ready queue. For a bounded queue with capacity K, the three semaphores would be `empty` initialized to K, `full` initialized to 0, and `mutex` initialized to 1. A deadlock could happen if a producer acquired the mutex before waiting for an empty slot while the queue was full, because a consumer would need the same mutex to remove an item and create an empty slot; acquiring the empty-slot semaphore before the mutex breaks the hold-and-wait condition.

**\*\*Classical problem and roles\*\***:

The classical problem is the Producer-Consumer problem. The main thread is initially a producer because it inserts the processes into the ready queue. CPU workers are consumers when they remove processes, and they become producers when they re-enqueue unfinished processes.

**\*\*Semaphores for a bounded queue (name and initial value)\*\***:

| Semaphore | Initial value | Purpose |
|---|---:|---|
| `empty` | K | Counts the available empty positions in the queue. |
| `full` | 0 | Counts the processes currently waiting in the queue. |
| `mutex` | 1 | Protects the shared queue so that only one thread accesses it at a time. |

**\*\*Deadlock scenario and prevention\*\***:

If a producer acquires `mutex` before waiting on `empty`, it can hold the mutex while the queue is full. A consumer then cannot acquire the mutex to remove a process and create an empty position. Both threads become unable to continue, resulting in deadlock. The hold-and-wait condition can be prevented by waiting on the required empty-slot semaphore before acquiring the mutex.

## Summary

**\*\*Key concepts I understood through these questions:\*\***

1. Race conditions happen when multiple threads access and modify shared data without proper synchronization.
2. ReentrantLock provides mutual exclusion and protects critical sections.
3. Counting semaphores coordinate producers and consumers while avoiding busy waiting.

**\*\*Concepts I need to study more:\*\***

1. Deadlock conditions and methods for preventing deadlocks.
2. Fairness, starvation, and bounded waiting in concurrent programs.


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
