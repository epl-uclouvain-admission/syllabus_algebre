# Instructions pour les Agents IA (`AGENTS.md`) — Syllabus d'Algèbre UCLouvain (EPL)

Ce dépôt contient le code source $\LaTeX$ complet du **Syllabus d'Algèbre** destiné à la préparation de l'épreuve d'algèbre de l'examen spécial d'admission aux études d'ingénieur civil à l'UCLouvain (École Polytechnique de Louvain — EPL).

## 1. Architecture des fichiers

- `main.tex` : Document maître (`\documentclass[11pt,a4paper,oneside]{book}`), définition des couleurs UCLouvain (`uclblue`, `ucllightblue`, `uclaccent`, `defgreen`, `exorange`, `warnred`), des boîtes `tcolorbox` (`theoreme`, `definition`, `exemple`, `attention`, `astuce`), de la page de titre TikZ et de l'avant-propos méthodologique.
- `chap1_polynomes.tex` : Polynômes, identités remarquables (dont Sophie Germain), second degré et relations Somme-Produit de Viète, division euclidienne, théorème du reste, schéma de Horner et paramètres de divisibilité.
- `chap2_equations_domaines.tex` : Valeurs absolues, équations irrationnelles $\sqrt{A(x)} = B(x)$ (et élimination des solutions parasites), domaines de définition et conditions d'existence (dont $\sqrt{\ln(U(x))}$ et $\frac{1}{\sqrt{\ln(U(x))}}$).
- `chap3_exp_log.tex` : Fonctions exponentielles et logarithmes en base quelconque, formule de changement de base, équations exponentielles et logarithmiques.
- `chap4_complexes.tex` : Nombres complexes dans $\mathbb{C}$ (forme cartésienne $a+bi$, conjugué $z^*$, forme polaire $\rho e^{i\theta}$, formule de De Moivre, racines $n$-ièmes dans le plan de Gauss).
- `chap5_combinatoire_probas.tex` : Analyse combinatoire (permutations, arrangements, combinaisons $\binom{n}{k}$, triangle de Pascal), formule du binôme de Newton, probabilités et paramètres statistiques (moyenne et écart-type).
- `chap6_suites.tex` : Suites arithmétiques et géométriques (terme général, moyennes, sommes $S_n$ et modélisation).
- `chap7_inequations_parametriques.tex` : Méthodologie et annales complètes pour la Question 2 de l'examen (discussion d'inéquations rationnelles, valeurs absolues et logarithmiques paramétriques, tableaux de signes).
- `chap8_systemes_problemes.tex` : Méthodologie et annales complètes pour la Question 3 de l'examen (problèmes textuels, systèmes linéaires, variable pivot, diagrammes de Venn à 3 ensembles, systèmes bilinéaires).
- `chap9_formulaire.tex` : Formulaire synthétique imprimable en exactement 4 pages A4 (`\newgeometry` + `\multicols{2}`).
- `annexe_logique.tex` : Annexe A sur le raisonnement logique, les opérations ensemblistes, les lois de De Morgan et les équivalences lors de la résolution d'équations.
- `chap10_correctifs.tex` : Corrigés détaillés de tous les exercices de fin de chapitre.
- `.github/workflows/build-pdf.yml` : Workflow GitHub Actions compilant automatiquement `main.tex`, générant l'artefact et publiant `main.pdf` et `syllabus_algebre_uclouvain.pdf` sur la release `latest`.

## 2. Règles d'édition et de qualité typographique

1. **Zéro dépassement de marge (`Overfull \hbox`) :**
   Après toute modification d'un fichier `.tex`, recompilez en deux passes et vérifiez l'absence totale d'avertissement `Overfull \hbox` :
   ```bash
   pdflatex -interaction=nonstopmode -file-line-error main.tex
   pdflatex -interaction=nonstopmode -file-line-error main.tex
   grep "Overfull" main.log
   ```
   Si une équation est trop large, découpez-la avec un environnement `align*` ou réduisez les espacements excessifs (`\qquad` $\to$ `\quad`).
2. **Conventions mathématiques de l'examen d'Algèbre EPL :**
   - Tous les calculs et exemples doivent être faisables **sans calculatrice**.
   - Le complexe conjugué de $z$ est noté $z^*$.
   - Les combinaisons sont notées $C_n^k$ ou $\binom{n}{k}$.
   - Les intervalles ouverts utilisent la notation belge/française $]a, b[$.
   - Mentionnez toujours explicitement la session et le numéro de question lorsqu'un exemple ou exercice provient des annales officielles (ex. `UCLouvain -- Juillet 2026, Q2`).
3. **Formulaire imprimable (`chap9_formulaire.tex`) :**
   Veillez à ce que chacune des 4 sections du formulaire tienne sur **exactement 1 page A4** (4 pages au total pour le Chapitre 9).
4. **Fichiers suivis par Git :**
   Les fichiers `.pdf` et les fichiers auxiliaires $\LaTeX$ (`*.aux`, `*.log`, `*.toc`, `*.out`) sont ignorés dans `.gitignore` car le PDF officiel est compilé et publié automatiquement par GitHub Actions lors de chaque `git push` sur `main`.
