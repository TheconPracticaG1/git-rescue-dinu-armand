
- Scenariu 1 (Mutare commit pe branch nou):** Am mutat un commit gresit de pe main pe un branch nou si am curatat branch-ul curent.
  - Comanda cheie: `git reset --hard HEAD~1` si crearea branch-ului separat.
- Scenariu 2 (Anulare bug fara rescrierea istoriei):** Am anulat efectul unui commit cu probleme pe un branch comun pastrand istoria intacta.
  - Comanda cheie: `git revert <hash> --no-edit`
- Scenariu 3 (Recuperare commit sters):** Am recuperat un commit pierdut in urma unui reset agresiv folosind jurnalul local.
  - Comanda cheie: `git reflog` urmat de `git switch -c recuperat-3 <hash>`
- Scenariu 4 (Eliminare fisiere sensibile):** Am scos un fisier `.env` cu secrete din repo si am documentat incidentul.
  - Comanda cheie: `git rm .env` si adaugarea in `.gitignore`
- Scenariu 5 (Documentare si ADR):** Am creat README-ul general si primul Architecture Decision Record pentru decizia de la Scenariul 2.
