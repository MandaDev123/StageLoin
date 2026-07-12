# Documentation — Site Vitrine Agence Digitale

> Site de présentation/publicité pour une agence de développement web & mobile, inspiré de la structure de [ichtus-it.com](https://www.ichtus-it.com/).
> Stack : **Next.js (React) + TypeScript**

---

## 1. Objectif du projet

Créer un site vitrine qui sert de **publicité** pour l'agence : présenter les services, prouver la crédibilité (portfolio, avis clients), et convertir les visiteurs en prospects via un formulaire de contact ou une prise de rendez-vous.

**Cibles** : startups, PME/TPE, entrepreneurs cherchant du développement web/mobile, du conseil IT, ou la création d'un MVP.

---

## 2. Stack technique proposée

| Élément | Choix |
|---|---|
| Framework | Next.js 14+ (App Router) |
| Langage | TypeScript |
| Styling | Tailwind CSS |
| Animations | Framer Motion |
| Formulaires | React Hook Form + Zod (validation) |
| Envoi d'email | Resend / Nodemailer / API route Next.js |
| CMS (optionnel) | Sanity, Contentful ou fichiers Markdown locaux |
| Hébergement | Vercel |
| Analytics | Google Analytics / Plausible |
| SEO | next-seo, sitemap.xml, robots.txt |

---

## 3. Arborescence des pages

```
/                 → Accueil
/services         → Détail des services
/portfolio        → Réalisations / projets
/portfolio/[slug] → Détail d'un projet
/a-propos         → L'agence, l'équipe, l'histoire
/blog             → Articles (optionnel)
/blog/[slug]      → Article détaillé
/contact          → Formulaire de contact / devis
/mentions-legales → Mentions légales
/politique-confidentialite → RGPD
```

---

## 4. Fonctionnalités par page

### 4.1 Page d'accueil
- [ ] **Hero section** : titre accrocheur, sous-titre, CTA principal ("Discutons de votre projet")
- [ ] **Bandeau logos clients / partenaires** (crédibilité, effet "vu dans")
- [ ] **Section services** : 3-4 cartes (Dev Web, Dev Mobile, Conseil IT, MVP/UI-UX) avec icônes et lien vers `/services`
- [ ] **Section "Pourquoi nous choisir"** : chiffres clés (nb projets, nb clients, années d'expérience) avec compteurs animés
- [ ] **Aperçu portfolio** : 3-4 projets phares en carrousel/grid, lien "Voir tous nos projets"
- [ ] **Témoignages clients** (carrousel)
- [ ] **Section processus** : étapes de collaboration (Idée → Design → Dev → Lancement → Suivi)
- [ ] **CTA final** avant footer (formulaire rapide ou bouton contact)
- [ ] **Footer** : liens réseaux sociaux, contact, mentions légales, newsletter

### 4.2 Services
- [ ] Liste détaillée des services (dev web, dev mobile React Native, conseil IT, MVP, UI/UX)
- [ ] Pour chaque service : description, technologies utilisées, cas d'usage, CTA "Demander un devis"
- [ ] Section FAQ (accordéon)

### 4.3 Portfolio
- [ ] Grille de projets filtrable (par catégorie : web / mobile / MVP)
- [ ] Fiche projet : contexte client, problématique, solution apportée, technos, résultats, screenshots/mockups
- [ ] Lien vers le site/l'app live si disponible

### 4.4 À propos
- [ ] Histoire de l'agence, mission, valeurs
- [ ] Présentation de l'équipe (photos, rôles, mini-bio)
- [ ] Localisation(s) (ex. France / Madagascar) avec carte
- [ ] Logos presse/médias si mentionné quelque part (BFM, etc.)

### 4.5 Blog (optionnel mais bon pour le SEO)
- [ ] Liste d'articles avec pagination
- [ ] Catégories/tags
- [ ] Temps de lecture, date, partage réseaux sociaux

### 4.6 Contact
- [ ] Formulaire (nom, email, téléphone, type de projet, budget, message)
- [ ] Validation des champs + messages d'erreur clairs
- [ ] Envoi d'email de confirmation à l'utilisateur + notification à l'agence
- [ ] Alternative : lien Calendly/Cal.com pour prise de rendez-vous direct
- [ ] Coordonnées (téléphone, email, adresse) + réseaux sociaux

---

## 5. Fonctionnalités transverses

- [ ] **Responsive design** (mobile-first)
- [ ] **Dark/Light mode** (bonus)
- [ ] **Animations au scroll** (fade-in, parallax léger)
- [ ] **Optimisation SEO** : balises meta, Open Graph, sitemap, données structurées (schema.org LocalBusiness)
- [ ] **Performance** : images optimisées (next/image), lazy loading, score Lighthouse > 90
- [ ] **Accessibilité (a11y)** : contrastes, navigation clavier, alt text
- [ ] **Multilingue** (FR/EN) si cible internationale — next-intl
- [ ] **Bandeau cookies / RGPD**
- [ ] **Chatbot ou widget WhatsApp** (contact rapide) — bonus
- [ ] **Newsletter** (Mailchimp/Brevo) — bonus
- [ ] **Back-office / CMS** pour éditer soi-même le contenu (portfolio, blog) sans coder

---

## 6. Roadmap suggérée

### Phase 1 — MVP (vitrine statique)
- Setup Next.js + Tailwind
- Pages : Accueil, Services, Portfolio, À propos, Contact
- Formulaire de contact fonctionnel
- SEO de base + responsive

### Phase 2 — Enrichissement
- Portfolio dynamique (CMS ou fichiers Markdown)
- Blog
- Animations avancées
- Analytics

### Phase 3 — Optimisation & croissance
- Multilingue
- A/B testing sur les CTA
- Intégration prise de RDV
- Optimisation SEO avancée / contenu

---

## 7. Structure de dossiers proposée (Next.js App Router)

```
src/
├── app/
│   ├── page.tsx                  → Accueil
│   ├── services/page.tsx
│   ├── portfolio/
│   │   ├── page.tsx
│   │   └── [slug]/page.tsx
│   ├── a-propos/page.tsx
│   ├── blog/
│   │   ├── page.tsx
│   │   └── [slug]/page.tsx
│   ├── contact/page.tsx
│   └── api/contact/route.ts      → API route envoi email
├── components/
│   ├── layout/ (Header, Footer, Navbar)
│   ├── ui/ (Button, Card, Accordion...)
│   └── sections/ (Hero, Services, Testimonials...)
├── lib/ (utils, envoi email, validation zod)
├── content/ (articles blog / projets en markdown, si pas de CMS)
└── public/ (images, favicon)
```

---

## 8. Prochaines étapes possibles
- Définir l'identité visuelle (logo, palette de couleurs, typographies)
- Rédiger les textes définitifs (copywriting) pour chaque section
- Lister 3-5 projets réels ou fictifs à mettre en avant dans le portfolio
- Choisir le nom de domaine et l'hébergement (Vercel recommandé avec Next.js)
