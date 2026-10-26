# DobrAppointment — prototype PWA v1

Application de démonstration, en français, pour coiffeur indépendant.

## Fonctionnalités
- Espace client : prestations, tarifs, dates (14 jours), créneaux, réservation.
- Espace coiffeur : rendez-vous, annulation, blocage de 30 minutes, statistiques, export CSV.
- Installation sur écran d'accueil après hébergement HTTPS, manifest et service worker.
- Fonctionne sans dépendance ni frais de licence.

## Tester
Hébergez les fichiers sur un site HTTPS (par exemple GitHub Pages). Pour tester sur ordinateur : `python -m http.server 8000`, puis ouvrez http://localhost:8000.

## IMPORTANT : version démo, pas encore un service de réservation public
Les données sont conservées dans le **localStorage de chaque navigateur** : les réservations faites sur le téléphone d'un client ne sont PAS visibles sur le téléphone du coiffeur. Le code administrateur `1234` est une simple démonstration, pas une authentification sécurisée. Ne collectez pas de véritables données clients sur cette version.

## Pour la mise en production
1. Ajouter une base de données partagée (ex. Supabase, offre gratuite sous limites).
2. Mettre en place un compte administrateur sécurisé et des règles d'accès (RLS).
3. Créer les réservations via une opération atomique côté serveur, avec contrôle anti-doublons.
4. Ajouter une politique de confidentialité, la suppression des données, et le traitement des données personnelles conformément au RGPD.
5. Tester les notifications et les annulations. SMS et domaine personnalisé sont facultatifs et potentiellement payants.
