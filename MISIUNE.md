# Scenariu 1 · Commit pe branch greșit · 30 XP

## Situația

Lucrezi repede și faci un commit pe branch-ul greșit.

## Ce faci

1. Ești pe `scenariu-1`. Adaugă în `config.json` câmpul `"legend": true`:
   ```json
   {
     "center": [28.03, 45.43],
     "zoom": 13,
     "legend": true
   }
   ```
2. Fă commit: `git commit -am "feat: add map legend"`. **Nu face push.**
3. Ups: commit-ul trebuia pe un branch nou, `feat/legenda`, nu pe `scenariu-1`.
4. **Mută commit-ul pe `feat/legenda`**, iar `scenariu-1` trebuie să rămână fără el.

## Ce predai

- Branch-ul `feat/legenda` urcat pe GitHub, cu commit-ul tău
- Pull Request `feat/legenda` → `scenariu-1`, cu titlul `Scenariu 1: ...`
- Pe GitHub, branch-ul `scenariu-1` **nu** are commit-ul `feat: add map legend`
- În descrierea PR-ului: comenzile rulate, în ordine, și de ce
