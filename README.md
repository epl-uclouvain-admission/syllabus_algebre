# Syllabus d'Algèbre — Examen d'admission UCLouvain (EPL)

[![Build LaTeX PDF](https://github.com/epl-uclouvain-admission/syllabus_algebre/actions/workflows/build-pdf.yml/badge.svg)](https://github.com/epl-uclouvain-admission/syllabus_algebre/actions/workflows/build-pdf.yml)

Bienvenue sur le dépôt officiel du **Syllabus d'Algèbre** destiné à la préparation de l'épreuve d'algèbre de l'**examen spécial d'admission aux études d'ingénieur civil** à l'[UCLouvain](https://uclouvain.be/fr/facultes/epl) (École Polytechnique de Louvain — EPL).

---

## 📥 Télécharger le syllabus (PDF)

Le document PDF est compilé automatiquement à chaque mise à jour du dépôt via GitHub Actions :

- 👉 **[Télécharger la dernière version du PDF (`syllabus_algebre_uclouvain.pdf`)](https://github.com/epl-uclouvain-admission/syllabus_algebre/releases/download/latest/syllabus_algebre_uclouvain.pdf)** *(lien direct issu de la dernière release)*
- 📄 Vous pouvez également consulter la page des **[Releases](https://github.com/epl-uclouvain-admission/syllabus_algebre/releases/tag/latest)** ou récupérer l'artefact généré dans l'onglet **[Actions](https://github.com/epl-uclouvain-admission/syllabus_algebre/actions)**.

---

## 📚 Contenu de l'ouvrage

Ce syllabus couvre l'ensemble de la matière d'algèbre, d'analyse combinatoire, de probabilités et de suites de 5e et 6e secondaire en Fédération Wallonie-Bruxelles (Communauté française de Belgique) nécessaire pour l'épreuve d'admission (qui se déroule **sans calculatrice**), ainsi que l'intégralité des exemples résolus et exercices issus des annales de l'examen d'entrée de l'UCLouvain (2021–2026) :

1. **Chapitre 1 — Polynômes, factorisation et division euclidienne** (`chap1_polynomes.tex`) : degré, racines, identités remarquables, relations somme-produit de Viète, division euclidienne de polynômes, théorème du reste, schéma de Horner et méthode des coefficients indéterminés.
2. **Chapitre 2 — Équations, valeurs absolues, radicaux et domaines d'existence** (`chap2_equations_domaines.tex`) : équations réductibles au second degré, équations et inéquations avec valeurs absolues $|A(x)|$, équations irrationnelles $\sqrt{A(x)} = B(x)$ (conditions de positivité et solutions parasites) et détermination de domaines de définition (fractions, racines et logarithmes composés).
3. **Chapitre 3 — Exponentielles et logarithmes : calculs, équations et bases variables** (`chap3_exp_log.tex`) : propriétés algébriques des puissances et logarithmes ($\ln$, $\log_{10}$, $\log_a$), formule de changement de base, équations exponentielles (par factorisation ou substitution $t = a^x$) et équations logarithmiques.
4. **Chapitre 4 — Nombres complexes dans $\mathbb{C}$** (`chap4_complexes.tex`) : forme algébrique (cartésienne) $a+bi$, conjugué $z^*$, module $|z|$, argument $\arg(z)$, forme trigonométrique et exponentielle d'Euler $\rho e^{i\theta}$, formule de De Moivre, racines $n$-ièmes dans $\mathbb{C}$ et équations mixtes en $z$ et $z^*$.
5. **Chapitre 5 — Analyse combinatoire, binôme de Newton et probabilités** (`chap5_combinatoire_probas.tex`) : principes additif et multiplicatif, permutations, arrangements, combinaisons $\binom{n}{k}$, triangle de Pascal, formule du binôme de Newton (recherche d'un coefficient ou du terme constant d'ordre nul), probabilités uniformes (dés, cartes, urnes, files d'attente), probabilité complémentaire et paramètres statistiques (moyenne et écart-type).
6. **Chapitre 6 — Suites arithmétiques et géométriques** (`chap6_suites.tex`) : terme général, moyenne arithmétique et géométrique, somme des $n$ premiers termes $S_n$, modélisation de phénomènes discrets (décroissance en pourcentage, amortissement, échelons, découpes, tarifs dégressifs).
7. **Chapitre 7 — Discussion d'équations et d'inéquations paramétriques** (`chap7_inequations_parametriques.tex`) : méthodologie complète pour la Question 2 de l'examen, mise sous forme standard $\frac{N(x,m)}{D(x,m)} \ge 0$, étude de l'ordre des valeurs critiques en fonction du paramètre réel $m$ ou $a$, tableaux de signes paramétriques et inéquations logarithmiques à base paramétrique $\log_{a-1}(P(x)) > 0$.
8. **Chapitre 8 — Mise en équations et systèmes algébriques (Problèmes textuels)** (`chap8_systemes_problemes.tex`) : méthodologie en 5 étapes pour la Question 3 de l'examen, systèmes linéaires $3\times 3$ et $4\times 4$ (pivot de Gauss et substitution structurée), diagrammes de Venn à 3 ensembles, systèmes bilinéaires (quantité $\times$ prix unitaire) et problèmes de flux/débits.
9. **Chapitre 9 — Formulaire récapitulatif** (`chap9_formulaire.tex`) : synthèse imprimable en 4 pages A4 de toutes les formules et méthodes essentielles d'algèbre.
10. **Annexe — Raisonnement logique, ensembles et méthodes de démonstration en algèbre** (`annexe_logique.tex`) : connecteurs logiques, lois de De Morgan, conditions nécessaires et suffisantes, équivalences lors de la résolution d'équations et opérations ensemblistes.
11. **Chapitre 10 — Corrigés détaillés des exercices** (`chap10_correctifs.tex`) : solutions complètes et commentées de tous les exercices de fin de chapitre.

---

## 🛠️ Compilation locale

Pour compiler le syllabus sur votre machine, vous devez disposer d'une distribution $\LaTeX$ complète (par exemple **TeX Live** ou **MacTeX**) incluant `pdflatex`, `latexmk` ainsi que les packages standards (`tikz`, `pgfplots`, `tcolorbox`, `amsmath`, `babel`, etc.).

Exécutez simplement la commande suivante à la racine du dépôt :

```bash
latexmk -pdf -interaction=nonstopmode main.tex
```

Ou avec `pdflatex` (deux passes sont nécessaires pour générer la table des matières et les références croisées) :

```bash
pdflatex main.tex
pdflatex main.tex
```

Le fichier généré s'intitule `main.pdf`.

---

## 👥 Auteurs, direction et sources

- **Direction artistique & *Prompt Engineering*** : L'équipe de l'examen d'admission à l'EPL — UCLouvain (**Jean-François Remacle** et **Pierre Schaus**).
- **Rédaction et mise en forme $\LaTeX$ / TikZ** : assistée par Intelligence Artificielle sous la supervision des enseignants.
- **Sources** :
  - Le programme officiel de mathématiques (5e et 6e secondaire, 6h/semaine) de la Fédération Wallonie-Bruxelles (Communauté française de Belgique).
  - Les supports des cours préparatoires et les annales officielles avec solutionnaires de l'épreuve d'**Algèbre** de l'examen d'admission de l'**UCLouvain** (2021 à 2026).

---

## 🤝 Signaler une coquille ou contribuer

Si vous repérez une coquille dans un énoncé, une figure ou un corrigé, n'hésitez pas à ouvrir une **[Issue](https://github.com/epl-uclouvain-admission/syllabus_algebre/issues)** ou à proposer une **[Pull Request](https://github.com/epl-uclouvain-admission/syllabus_algebre/pulls)**.
