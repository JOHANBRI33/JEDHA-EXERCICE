# Prompts utilisés

## Prompt Cmd+K pour la section Features

> Remplace le contenu de cette section `#features` (y compris le `<h2>` vide et le commentaire) par une grille de 3 cartes de fonctionnalités. Stack : HTML + Tailwind Play CDN (déjà chargé). Layout : `grid grid-cols-1 md:grid-cols-3 gap-6`. Chaque carte est un `<article>` avec : `rounded-2xl bg-white/[0.03] border border-white/10 backdrop-blur p-6`, effet hover `hover:-translate-y-1` avec `transition`. Dans chaque carte : une boîte d'icône SVG (`grid size-12 place-items-center rounded-xl bg-violet-500/10 ring-1 ring-violet-400/20`), un `<h3>` titre, un `<p>` descriptif en `text-sm text-slate-400`. Ajoute un `<h2>` de section au-dessus de la grille. Texte exact des cartes :
>
> 1. **Musique live chaque soir** — Du coucher au lever du soleil, assez fort pour couvrir la voix d'un chasseur de primes.
> 2. **Contrebandiers bienvenus** — Aucune question posée. Banquettes au fond, aucun registre tenu.
> 3. **Droïdes : voir le règlement** — Limites sur la piste. Mise en veille recommandée.

## Corrections post-génération

1. **Suppression de `backdrop-blur-xl`** : remplacé par `backdrop-blur` seul. Avec le CDN Tailwind v3, `backdrop-blur-xl` fonctionne mais `backdrop-blur` (8px) suffit sur un fond quasi-opaque ; la variante `xl` (24px) n'apportait aucune différence visible ici.
2. **Remplacement de `shadow-sm` sur les cartes** : retiré car sur un fond sombre à très faible opacité (`bg-white/[0.03]`), une ombre légère n'a aucun effet visible. Le `border border-white/10` assure déjà la séparation visuelle.
3. **Ajout de `transition`** : la classe `hover:-translate-y-1` seule ne produit pas d'animation fluide sans `transition` (ou `transition-transform`). Ajouté `transition` pour que l'effet de levée soit progressif.
Place la section #features à l'intérieur du <main>, juste après la section hero (après son </section>), pas avant le main. Garde exactement les textes demandés.