---
title: 'TAPAAL Exercises'
author: Shahab Shajarat
date:
---

---

\centering
# Exercise 0 (for Petri net newbies)

Draw a Petri net model of an elevator that can move up and down in a building with four floors. For example, when the elevator is at the 2nd floor, it can move up to the 3rd floor or down to the 1st floor. Enter the simulation mode to examine the possible behaviours.

\raggedright

**Solution:**

\centering

![](https://i.imgur.com/9YruxVR.png){ width=25% }

a) Model the fact that moving up or down one floor takes 3 seconds. Formulate
a query asking if it is possible for the elevator to move from the 1st floor to the 4th floor in less than 8 seconds. It this possible in 9 seconds? In the query dialog select ”Some encountered trace” so that you can see the schedule.

\raggedright

**Solution:**

\centering

![](https://i.imgur.com/v0tQbdE.png){ width=30% }

b) Can you modify your model so that after moving up it has to reach the top
floor of the building before it can start moving down again?

\raggedright

**Solution:**

\centering

![](https://i.imgur.com/YP69JKR.png){ width=30% }

---

# Exercise 1

Assume four constants $s1, s2, s3$ and $sum$. Design a net with a query such that the query is satisfied if and only if $s1 + s2 + s3 = sum$. Verify the query for the values.

a) $s1 = 3, s2 = 6, s3 = 7$ and $sum = 16$, and
b) $s1 = 2, s2 = 3, s3 = 4$ and $sum = 10$.

Make sure that you have enough extra tokens to get a conclusive result (use the check for boundedness in the query dialog).  
***Hint:*** you can use either the ages of tokens for checking the sum, or the exercise can be solved completely without using any time features (you are welcome to implement both solutions)!

\raggedright

**Solution:**

\centering

![For, $s1 = 3, s2 = 6, s3 = 7$ and $sum = 16$](https://i.imgur.com/eXDRstA.png)

\raggedright

**Solution:**

\centering

![For, $s1 = 2, s2 = 3, s3 = 4$ and $sum = 10$](https://i.imgur.com/7FYQbOL.png)

---

# Exercise 2

Consider a workflow that consists of six tasks $T0, T1, ..., T5$ and the following constraints.

- The workflow has to start with the task T0 that has a duration between 2
to 3 time units.
- After that the tasks $T1, T2$ and $T3$ can be performed in parallel and their durations belong to the intervals $[2,6], [5,8]$ and $[2,5)$, respectively.
- Task $T4$ of duration 0 can be performed earliest 2 time units after both $T1$ and $T2$ are finished.
- Task $T5$ of duration 0 can be performed as soon as the tasks $T4$ and $T3$ and finished, but no later then 4 time units after the task $T3$ was finalized. After that the workflow is finished.

a) Is it possible to find a schedule of tasks satisfying all the constraints given above? Use TAPAAL to model the workflow and formulate a query to answer this question (ask for a trace in the query dialog so that you can examine the schedule in the simulator).

\raggedright

**Solution:**

\centering

![](https://i.imgur.com/oxKL7lD.png)

b) Assume now that the task $T3$ has additionally a global deadline requiring that it has to be finished no later than 4 time units after the workflow was initiated. Is it still possible to find a schedule of all the tasks?

\raggedright

**Solution:**

\centering

![](https://i.imgur.com/CCGyoIG.png)

---

# Exercise 3

Consider a train level crossing. The trains can arrive in arbitrary intervals and in a good distance from the crossing they activate a sensor, initiating a process that is stopping the cars from entering the crossing. The cars entering the crossing
can see a green, yellow or red color on the traffic controller. When the train proximity censor is activated, the traffic light goes immediately from green to yellow, and after another 5 seconds enters the red color, where it stays exactly for 30 seconds, after that returning back to green. Should the next train arrive when the color is yellow, no action is taken, however, when it arrives when the light is red, the red-duration period of 30 seconds is reset and starts counting an additional 30 seconds period while the light remains red. Trains arriving to the crossing have a difference speed, so it takes between 20 to 25 seconds before
the train arrives at the crossing, then it takes another 3 to 6 seconds to pass the crossing.

a) Model the train level crossing in TAPAAL and ask a query whether it is possible that the traffic light is green or yellow while a train is in the danger zone (moving through the crossing). Verify the query for 3, 4 and 5 trains.

\raggedright

**Solution:**

\centering

![](https://i.imgur.com/x9LoorM.png)

b) Was the red light duration sufficient? If not try to find the minimum delay that ensures that the crossing is save. Does the minimum duration change with the number of trains?

\raggedright

**Solution:**

\centering

![Minimum delay = 32](https://i.imgur.com/CzLko0r.png)
