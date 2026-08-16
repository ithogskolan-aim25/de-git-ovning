# Git-övning — Vecka 2
 
Detta är ett "sandlåderepo" där innehållet är oviktigt, poängen är att ni ska kunna testa att använda github utan att det finns risk för att ha sönder något.
 
## Del 1 — Att göra en pull request
 
Det här är ett mönster du ofta kommer att använda i kursen och utanför den.
 
1. Klona det här repot till din utvecklingsmiljö (Codespaces eller din laptop)
2. Skapa en gren (branch) som har samma namn som till git-användarnamn: `git switch -c <your-username>`
3. Skapa en fil `deltagare/<ditt-användarnamn>.md`. Kopiera mallen från 
   `deltagare/EXEMPEL.md` och fyll i den.
4. Gör commit och push: `git add`, `git commit -m "..."`, `git push -u origin <ditt-användarnamn>`
5. Öppna en PR, pull request, mot `main` on GitHub.
6. **Be din partner granska din PR.** De måste lämna minst två kommentarer på dina ändringar.
7. Lös minst en av kommentarerna, pusha ändringen, och gör merge på din egen PR.
 
Du får inte göra merge utan att minst en person har godkänt det. Det är samma regel som många professionella organisationer använder, och det ser till att man inte hoppar över kodgranskningen bara för att man känner sig stressad.
 
## Del 2 — Merge-konflikter
 
Öppna `par/par-XX.md` där XX är numret på det par du är i. Den har två TODO-rader i sig.
 
Ni ska båda redigera **samma rader**, samtidigt, på separate grenar.
 
1. Båda parterna: gör en ny gren från `main` (`git switch main && git pull && git switch -c par-XX-<name>`)
2. Båda parterna: fyll in **båda** TODO-raderna med era egna svar utan att koordinera. Gör commit och push.
3. Båda parterna: öppna en PR mot `main`.
4. För den första som mergear händer ingenting - koden inkorporeras i main.
5. För den andra säger GitHub nu: *"This branch has conflicts that must be
   resolved."* Denna person behöver fixa det:
 
   ```
   git switch main
   git pull
   git switch par-XX-<name>
   git merge main          # konflikten kommer här
   # editera filen: behåll båda svaren, radera markörerna <<<<<<< ======= >>>>>>>
   git add par-XX.md
   git commit
   git push
   ```
 
6. PR:en bör nu leda till en ren merge.
 
Lärdomen är att en merge-konflikt inte är ett fel och att inget är trasigt. Det är git som berättar för oss att två olika personer ändrade samma rader och att den inte vill gissa vad som är "rätt svar". 
 
## Om något går fel

- Testa `git status` och kolla om det ger ledtrådar
- `git remote -v` visar vart du pushar dina ändringar
 

