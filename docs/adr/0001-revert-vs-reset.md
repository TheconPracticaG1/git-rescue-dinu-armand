# ADR-0001: Folosirea lui git revert in loc de git reset pentru corectarea bug-urilor pe branch-uri comune

## Context
Pe un branch partajat cu alti colegi, un commit cu un bug a ajuns in istoric. Era nevoie de anularea modificarii fara a strica sincronizarea echipei.

## Decizie
Am ales sa folosim `git revert` in loc de `git reset`. Aceasta comanda adauga un commit nou care inverseaza modificarile, in loc sa stearga commit-urile anterioare din istoric.

## Consecințe
Istoricul ramane curat si liniar, fara a fi nevoie de `git push --force`. Colegii care au deja branch-ul tras local nu vor avea conflicte sau istorice divergente la urmatorul pull.
