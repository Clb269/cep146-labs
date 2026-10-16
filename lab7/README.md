
# CEP146 – Lab 7
Student: Aayan Bhandari
GitHub Username: Clb269

## Exercise 1: Personal Portfolio Merge Conflict

I created a Git repository called my-portfolio and added portfolio.md.

I created two branches with different changes to the Skills section:
- main: C++, JavaScript, Git Advanced, and SQL
- desktop-updates: Python, Java, Git Intermediate, HTML, and CSS

When I ran git merge desktop-updates, Git reported a conflict in portfolio.md.

I resolved the conflict by combining both sets of skills, removing the conflict markers, and committing the result.

Final Skills section:
- Programming: Python, Java, C++, JavaScript
- Git: Advanced
- Web Development: HTML, CSS
- Database: SQL

Verification command:
git log --oneline --graph --all

Merge commit: fc50a99

### Reflection Questions

1. Why did the conflict occur?

The conflict occurred because I changed the same Skills section differently in the main and desktop-updates branches. Git could not automatically decide which changes to keep.

2. What would have prevented this conflict?

Coordinating changes, updating branches regularly, and avoiding simultaneous changes to the same lines could have prevented this conflict.

3. In real life, how do you avoid conflicts when working on multiple devices?

I would use git pull before beginning work, commit changes regularly, and use git push before switching devices.

4. What was the most challenging part of resolving the conflict?

The most challenging part was combining both versions correctly while removing the conflict markers and preserving the rest of the portfolio.

5. How did Git help you identify where the conflict was?

Git reported a conflict in portfolio.md and inserted conflict markers that showed the competing changes.

## Exercise 2: Recipe Bug Hunt with Git Bisect

I created a Git repository called recipe-bug-hunt and added cookies.txt.

I created seven commits:
1. Add original recipe
2. Add ingredient amounts
3. Add mixing instructions
4. Add yield information
5. Update recipe format
6. Add baking tips
7. Add storage instructions

The recipe temperature was correct (350°F) in Commits 1–4 and incorrect (450°F) in Commits 5–7.

I used Git Bisect to identify the first bad commit.

Commands used:
git bisect start
git bisect bad
git bisect good HEAD~6
git bisect good
git bisect bad
git bisect bad
git bisect reset

First bad commit: ec57bdc
Commit 5: Update recipe format

I corrected the temperature back to 350°F and committed the fix.

Correction commit: 85abb06
Fix: Correct temperature back to 350°F

### Reflection Questions

1. How many times did you check the temperature before Git found the bug?

I tested three intermediate commits: Commit 4, Commit 6, and Commit 5. Commit 4 was good, while Commits 6 and 5 were bad.

2. If you had 100 commits instead of 7, approximately how many checks would Git Bisect need?

Approximately 7 checks, because Git Bisect uses binary search.

3. How is Git Bisect different from manually checking each commit?

Git Bisect uses binary search to narrow down the problem efficiently, while manual checking may require examining many commits one by one.

4. When would Git Bisect be most useful in real projects?

Git Bisect is useful when a bug appears in a project with many commits and the developer does not know which commit introduced it.

5. What information do you need to start a Bisect session?

I need one known good commit and one known bad commit, along with a way to determine whether a version contains the bug.

## Conclusion

I completed both main exercises of Lab 7, including creating and resolving a merge conflict and finding a bug using Git Bisect. Supporting screenshots and final project files are included in this folder.
  
