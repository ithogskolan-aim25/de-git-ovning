# Git-övning — Week 2
 
A throwaway repo. Nothing here matters, which is the point: you can break it.
 
Everything you do today you will do again for real during the project, on a repo
where mistakes cost something. Today they cost nothing.
 
## Part 1 — Your own file (the everyday flow)
 
This is the loop you will use every day for the next seven weeks.
 
1. Clone this repo **inside your Codespace** (not onto the laptop):
   `git clone <repo-url>`
2. Create a branch named after yourself: `git switch -c <your-username>`
3. Create a file `deltagare/<your-username>.md`. Copy the template from
   `deltagare/EXEMPEL.md` and fill it in.
4. Commit and push: `git add`, `git commit -m "..."`, `git push -u origin <your-username>`
5. Open a pull request against `main` on GitHub.
6. **Ask your partner to review it.** They must leave at least two comments that
   say something — "looks good" is not a review.
7. Address at least one comment, push the fix, then merge your own PR.
 
You cannot merge without an approval. That is deliberate: it is the same rule
most professional teams run, and it is the reason code review does not get
skipped when someone is in a hurry.
 
## Part 2 — The merge conflict (in pairs)
 
Find your pair number and open `par/par-XX.md`. It has two TODO lines in it.
 
Both of you will edit **the same lines**, at the same time, on separate branches.
That is not a mistake — it is the setup.
 
1. Both partners: branch off `main` (`git switch main && git pull && git switch -c par-XX-<name>`)
2. Both partners: fill in **both** TODO lines with your own answers. Do not
   coordinate. Commit and push.
3. Both partners: open a PR against `main`.
4. Whoever merges first — nothing happens. It just merges.
5. The second one: GitHub now says *"This branch has conflicts that must be
   resolved."* That person resolves it:
 
   ```
   git switch main
   git pull
   git switch par-XX-<name>
   git merge main          # the conflict appears here
   # edit the file: keep both answers, delete the <<<<<<< ======= >>>>>>> markers
   git add par-XX.md
   git commit
   git push
   ```
 
6. The PR now merges cleanly.
 
**The lesson is in step 5.** A merge conflict is not an error and nothing is
broken. Git is telling you that two people changed the same lines and it will
not guess which one you meant. The second person to merge always resolves — and
in a team, that will be you about half the time.
 
## When things go wrong
 
- **Pushed and it went somewhere unexpected?** Run `git remote -v` and check the
  URL. If it points at your own username instead of the course org, your push
  created a personal fork. Say so — it is a five-second fix and it is worth
  everyone seeing it once.
- **Committed to `main` by accident?** Tell me. Do not try to fix it with
  `git reset --hard`.
- **Stuck?** `git status` says more than people expect. Read it before asking.
