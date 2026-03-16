# HiBroker Advice — Récapitulatif V1 & Cadrage V2

---

## 1. Ce qui a été livré (V1)

### Plateforme & Infrastructure

- Application web complète déployée (Next.js + Supabase + Vercel)
- Plus de 40 routes fonctionnelles (pages + API)
- Authentification sécurisée avec Row-Level Security (chaque courtier ne voit que ses données)
- Stockage sécurisé et chiffré des tokens OAuth

---

### Onboarding

- Parcours en 7 étapes : compte, informations cabinet, connexion Google Business, identité visuelle, paramètres IA, confirmation, configuration
- Upload photo de profil et logo
- Connexion automatique Google Business Profile

---

### Campagnes de sollicitation

- Envoi manuel d'emails de sollicitation depuis la boîte pro du courtier (Gmail via OAuth)
- Import CSV pour campagnes en masse avec espacement automatique des envois
- Séquence de relances automatiques : J+0, J+2, J+5
- Arrêt automatique si le client interagit
- Templates email HTML personnalisés avec logo et couleurs du cabinet

---

### Page de collecte d'avis (client-facing)

- URL unique par courtier, partageable par email ou site web
- Page minimaliste avec logo du cabinet
- Choix satisfait / insatisfait
- Routing intelligent : satisfait → redirection vers la fiche Google pour déposer un avis, insatisfait → formulaire interne

---

### Gestion des avis

- Dashboard centralisé avec tous les avis internes collectés
- Scraping automatique des avis Google via Apify (import quotidien)
- Analyse IA de chaque avis : score de sentiment, détection de thèmes (Délai, Prix, Communication, Disponibilité, Conseil, Suivi, Sinistres, Accueil)
- Génération de réponses IA en 3 tons : Professionnel, Empathique, Direct
- Le courtier peut éditer la réponse avant d'envoyer

---

### Alertes client (conformité ACPR/FSMA)

- Registre des réclamations conforme aux exigences réglementaires
- Upload de la procédure de réclamation du courtier (PDF/TXT), utilisée comme contexte par l'IA
- Export Excel pour contrôle ACPR/FSMA
- Suivi de statut par alerte (Nouveau, Traité)

---

### Monitoring concurrentiel

- Détection automatique de concurrents par zone géographique
- Suivi de la note moyenne et du volume d'avis des concurrents
- Comparaison avec les performances du courtier

---

### Analytiques

- Tableau de bord avec KPIs : taux de réponse, évolution des avis, score moyen
- Vue d'ensemble de l'activité campagnes et avis

---

## 2. Corrections & améliorations livrées en V2

- Correction de l'upload photo de profil
- Correction de l'upload logo dans les paramètres
- Simplification du flux de connexion Google Business Profile (recherche par nom + ville au lieu d'un lien Maps)
- Champ identifiant entreprise dynamique selon le pays (SIREN pour la France, BCE pour la Belgique)

---

## 3. Prochaines étapes pour compléter le MVP

- Intégration de l'envoi email via Microsoft 365 / Outlook (OAuth + Microsoft Graph API)
- Intégration Stripe pour la gestion des abonnements et paiements
- Vérification OAuth Google
