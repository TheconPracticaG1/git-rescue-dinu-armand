# Scenariu 3 · Commit „pierdut” · 40 XP

## Situația

Lucrezi o oră, faci trei commit-uri, apoi rulezi `git reset --hard` cu un număr greșit și „pierzi” două dintre ele, înainte să le fi urcat. Aproape nimic nu se pierde în Git: le găsești.

## Ce faci

1. Ești pe `scenariu-3`. Fă tu cele trei commit-uri, exact așa:
   ```bash
   echo "strat: apa" >> harta.txt
   git add harta.txt
   git commit -m "feat: add water layer"

   echo "cautare: strada" >> harta.txt
   git commit -am "feat: add street search"

   echo "comutator straturi: da" >> harta.txt
   git commit -am "feat: add layer toggle"
   ```
2. Verifică: `git log --oneline` arată cele trei commit-uri. **Nu face push.**
3. Greșeala: `git reset --hard HEAD~2`. Acum `feat: add street search` și `feat: add layer toggle` au dispărut din `git log`, iar `harta.txt` are un singur rând.
4. Recuperează commit-ul `feat: add layer toggle` doar din ce ai local: nu există nicio copie pe GitHub.
5. Pune-l pe un branch nou, `recuperat-3`, și urcă-l.

## Ce predai

- Branch-ul `recuperat-3`, care conține commit-ul `feat: add layer toggle` (iar `harta.txt` are toate cele trei rânduri)
- Pull Request `recuperat-3` → `scenariu-3`, cu titlul `Scenariu 3: ...`
- În descrierea PR-ului: **outputul comenzii cu care ai găsit commit-ul** (copiat ca text) și comenzile rulate
