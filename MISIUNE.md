# Scenariu 2 · Bug pe un branch comun · 40 XP

## Situația

Un coleg a pus pe `scenariu-2` commit-ul `feat: change default zoom`. Zoom-ul a ajuns 999 și harta nu se mai vede. Branch-ul e comun: alți colegi l-au tras deja la ei.

## Ce faci

Anulează efectul commit-ului `feat: change default zoom` **fără să rescrii istoria**. Istoria lui `scenariu-2` trebuie să rămână exact cum e, doar cu un commit în plus.

## Ce predai

- Un branch `fix/zoom`, creat din `scenariu-2`, cu rezolvarea
- Pull Request `fix/zoom` → `scenariu-2`, cu titlul `Scenariu 2: ...`
- În descrierea PR-ului: comenzile rulate și **de ce nu ai folosit `git reset`**
