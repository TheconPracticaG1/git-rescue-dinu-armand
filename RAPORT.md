Raport incident: expunere fisier .env in repository

1. Invalidarea cheii API si schimbarea parolei imediat:** Din momentul in care `.env` a ajuns pe GitHub, cheia si parola sunt deja compromise (exista boti care scaneaza repo-urile automat). Primul pas e sa le dezactivam si sa generam altele noi.
2. Ce nu pot face singur si cine trebuie sa faca:**
   DevOps / Adminul de sistem / Tech Lead-ul:** Ca simplu dev sau practicant de obicei nu am acces la conturile de productie sau la consola unde se genereaza cheile API si parolele de baza de date. Trebuie sa anunt urgent adminul sau tech lead-ul ca sa roteasca secretele in productie si sa verifice log-urile sa vada daca a apucat cineva sa le foloseasca.
   Adminul repo-ului de GitHub:** Daca branch-ul e protejat, doar cineva cu drepturi de admin poate debloca branch-ul ca sa rescriem istoria pe remote si sa stearga cache-ul/PR-urile unde mai apare commit-ul.
3. Ce fac eu in repo ca sa nu se mai repete:** Sterg `.env` din Git (`git rm .env`), adaug `.env` in `.gitignore` ca Git sa-l ignore pe viitor, si eventual pun un `.env.example` cu cheile goale ca sa stie colegii ce variabile trebuie setate local.
4. Stergerea din tot istoricul Git:** Daca e nevoie sa dispara urma fisierului din repo, se foloseste un tool gen `git filter-repo` sau `BFG Repo-Cleaner` care rescrie toata istoria fara `.env`, apoi se face force push coordonat cu toata echipa.

2. De ce nu e suficient doar sa stergem fisierul intr-un commit nou

Pentru ca Git pastreaza toata istoria commit-urilor. Daca doar sterg `.env` si fac un commit nou, fisierul dispare din folderul curent, dar **ramane salvat in commit-ul vechi**. Oricine intra pe GitHub la tab-ul de Commits sau da `git log -p` vede exact ce linii au fost adaugate anterior s

2. De ce stergerea fisierului intr-un commit nou NU este suficienta
Git pastreaza intregul istoric al proiectului. Daca stergem `.env` printr-un commit nou (`git rm .env` + `git commit`), fisierul dispare doar din starea curenta (`HEAD`), dar **ramane vizibil in continuare in commit-ul anterior** din istoria Git. Oricine are acces la repository (sau boții care scaneaza automat GitHub-ul in timp real) poate rula `git log -p` sau poate deschide commit-ul vechi pe GitHub si vedea cheia API si parola in clar.
