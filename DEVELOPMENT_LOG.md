# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent
**Requirements**: Minimum 5 entries showing progression over time.
---
## Your Development Log:

### Entry 1 - [23 mars 2026 and Time: 11 am]
**What I did**: create github account and repository setup

**Details**:  created an account on GitHub by signing up with my university email and choosing a username and password.
After verifying my email, and rename repository file .

**Challenges**: not hard it was super easy 

**Solution**: -

**Time spent**: 3-5 minutes 

---

### Entry 2 - [24 mars 2026 and Time: 10 am]
**What I did**: download VS code and link IDE to repository, also install extensions. 

**Details**: First, I go to the VS Code website and download it, then install it normally.

After that, I open VS Code and make sure I have Git installed on my computer.

To connect to a repository, I press Ctrl + Shift + P, type Git: Clone, paste the repo link, and open the project.

Then, I install extensions , searching for what I need, and clicking Install.

Finally, I sign in to GitHub from VS Code so everything syncs.

**Challenges**:  might face some small issues, like Git not working.

Extensions may fail to install or cause conflicts.
**Solution**: Git not working: Reinstall Git and restart VS Code.
 • Extensions issues: Restart VS Code or reinstall the extension.
 
**Time spent**: 10-15 minutes
---
### Entry 3 - [25 mars 2026 and Time:11;30 am ]
**What I did**: Feature 1: Add Process Priority 

**Details**: I added a priority field to the Process class and generate it randomly when creating a process.

**Challenges**: Display formatting might be tricky.

**Solution**: I fixed the display issue by using string formatting

**Time spent**: 30-45 minutes
---
### Entry 4 - [26 mars 2026 and Time: 1pm]
**What I did**: Feature 2: Count Context Switches

**Details**:addeding a static counter for context switches, increment it each time a new process starts, display the total at the end.

**Challenges**: Making sure the counter updates exactly when a new process starts.

**Solution**: Incremented the counter inside the process start logic to track every switch correctly

**Time spent**: 20-30 minutes 

---

### Entry 5 - 28 mars 2026 and Time:]
**What I did**: Feature 3: Track Waiting Time

**Details**: I added fields to track process creation time and total waiting time, calculated waiting time for each process, and showed a summary table at the end with name, burst time, and waiting time.

**Challenges**: Tracking time accurately and updating waiting time for each process

**Solution**: Used System.currentTimeMillis() to record creation and calculate waiting time correctly for every process.

**Time spent**: 1-2 hours 
---------
## Summary
- Set up GitHub repo — easy, 5 min
- Download VS Code, link repo, install extensions — Git/extensions issues fixed by reinstalling, 10–15 min
 - Add process priority & display it — fixed formatting with string formatting, 30–45 min
 - Count context switches — incremented in process start, 20–30 min
-Track waiting time & summary table — used System.currentTimeMillis(), 1–2 hours

Total time spent on assignment: ~5-7 hours

Most challenging part: Tracking waiting time accurately for each process and updating it in real-time.

Most interesting learning: Adding process priorities and seeing how context switches and waiting times affect the scheduling behavior—it made me understand process management better.
What I would do differently next time: Next time, I would plan the features step by step, test each one as I go, and track waiting time more efficiently to save time and avoid errors.





**What I would do differently next time**: 
