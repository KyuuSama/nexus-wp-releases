[🌐 English](README.md) | [🇫🇷 Français](README.fr.md)

# NEXUS-WP (v0.3-Alpha)
> Système d'exploitation modulaire, intégrateur de code isolé et console de pilotage SaaS pour WordPress.

NEXUS-WP est un framework d’ingénierie et d’optimisation universel pour WordPress. Conçu pour s'affranchir des limites des thèmes et des constructeurs de pages, il combine un moteur d'exécution local ultra-léger, une console d'administration épurée et un couplage SaaS hautement sécurisé pour automatiser l'affichage des données, l'intégration de scripts personnalisés et la sauvegarde Cloud unifiée.

---

## 🚀 LES 4 PILIERS DE NEXUS-WP

### 1. L’Atelier (Édition de Code & Générateurs)
L'Atelier est l'espace de création et de développement sur-mesure de l'extension. Il garantit une étanchéité totale entre le cœur du système et vos modifications.

*   **Intégrateur de Code Custom (PHP, CSS, JS)** : Permet d'injecter vos scripts personnalisés de manière isolée de l'infrastructure d'usine.
    *   *Sécurisation de portée* : Injection automatique des directives de sécurité WordPress sur les scripts PHP créés pour interdire toute exécution directe par URL.
    *   *Rotation d'Historique de Secours* : Génération d'une copie de sauvegarde locale avant chaque écriture, avec un système de rotation intelligente (FIFO) pour préserver l'espace disque.
    *   *Aide à la Saisie (Prettycode & Minify)* : Outils d'optimisation intégrés pour reformater (indenter) ou compresser (minifier) instantanément vos codes CSS et JS.
*   **Générateur de Composants (Hub Cards)** : Permet de concevoir des composants d'affichage responsives et adaptatifs en grille (`half`, `third`, `full`) dotés d'un panneau de prévisualisation synchronisé en temps réel (`NEXUS-SYNC`).
    *   *Shortcode Maître `[nexus_card id="X"]`* : Appelle le composant, charge sa structure d'usine et résout dynamiquement ses variables (redirections, cibles d'ouverture, gestion de logos).
*   **Générateur de Shortcodes Sémantiques** : Permet de convertir vos structures d'Atelier en shortcodes réutilisables de manière autonome.

---

### 2. L’Arsenal (Composants Prêts à l'Emploi)
L'Arsenal rassemble un catalogue d'outils d'usine activables en un clic pour surcharger et corriger le comportement de votre thème ou de vos extensions :

*   **Hygiène & Structure** : Scripts d'optimisation de recherche globale, masquage de barres d'outils ou sidebar intelligente.
*   **Design & Templates (Surcharges d'usine)** :
    *   *Optimisations Elementor* : Améliorations de grilles responsives et effets de flous d'arrière-plan (*glassmorphism*).
    *   *Habillages de Badges* : Mise en forme solide et transitions élégantes au survol pour les expertises, statuts ou notations.
    *   *Recherche AJAX* : Améliorations de contrastes et titres asymétriques pour le widget de recherche.
    *   *Pagination améliorée* : Script d'observation dynamique (`MutationObserver`) et mise en forme active.
    *   *Images de substitution* : Génération automatique de filigranes textuels dynamiques sur les images par défaut si l'image à la une est absente.

---

### 3. Le Moteur de Données Universel (`[nx_field]`)
NEXUS-WP intègre un routeur universel d'extraction, de mise en forme et de sécurisation des données du site public à l'aide d'un unique shortcode `[nx_field]` doté de 14 aiguillages logiques :

1.  **`text`** : Extraction et formatage de chaînes de caractères (téléphones, devises) avec sécurité anti-crash de conversion d'Array.
2.  **`wysiwyg`** : Rendu de paragraphes de textes riches avec interprétation récursive des shortcodes imbriqués.
3.  **`link`** : Générateur de boutons de liens dynamiques (téléphone, e-mail, WhatsApp, web) avec icônes de librairies et gestion de secours (`fallback`).
4.  **`fallback`** : Intercepteur de contenu vide (affiche un texte alternatif ou le contenu entre les balises du shortcode).
5.  **`taxonomy`** : Rendu de badges taxonomiques hiérarchiques avec algorithme de priorité enfant.
6.  **`class`** : Concaténateur dynamique de classes CSS basées sur les slugs de taxonomies de la fiche courante.
7.  **`contact`** : Parseur de contacts structurés (détecte et convertit les e-mails et téléphones dans une chaîne séparée par un délimiteur).
8.  **`list`** : Générateur de grilles de badges basées sur plusieurs champs différents.
9.  **`url`** : Extraction de l'URL de la page canonique courante.
10. **`related`** : Moteur de requêtes relationnelles croisées pour lister les IDs des publications liées.
11. **`icon`** : Injecteur d'icônes multi-librairies (FontAwesome, Bootstrap Icons, Dashicons).
12. **`if`** & **`nx_if`** : Portes logiques conditionnelles pour afficher un contenu uniquement si une valeur existe (ou si elle n'existe pas via l'attribut `not="true"`).
13. **`image`** : Gestionnaire d'images adaptatif avec image de secours et texte ALT automatique basé sur le titre de la fiche active.
14. **`term_list`** : Liste brute de termes taxonomiques sans exclusion pour l'affichage de tags.

---

### 4. Logistique & Nexus Cloud (Le Moteur SaaS)
Le pilier Logistique connecte l'extension locale à l'infrastructure SaaS centralisée de NEXUS via un protocole chiffré ultra-léger et asynchrone :

*   **Connexion d'Onboarding** : L'utilisateur se connecte à l'aide de ses identifiants classiques (E-mail/Mot de passe) au sein d'une Iframe SaaS sécurisée. Le serveur central valide l'accès, génère le jeton technique et le transmet de manière étanche à WordPress.
*   **Sécurisation des Quotas en RAM** : Le système s'appuie sur une signature de sécurité unifiée et masquée en mémoire vive (RAM), interdisant tout contournement ou modification manuelle locale des quotas de licence.
*   **Database Transaction Lock (Garde-fou absolu)** : Avant toute écriture physique dans la BDD locale (sauvegarde de licence, d'options globales ou de configurations d'Atelier), le système valide la cohérence structurelle du registre. Si le fichier est corrompu ou incomplet, la transaction est immédiatement avortée pour protéger le site de tout crash.
*   **Sauvegardes et Restaurations Cloud** : Permet de compresser l'intégralité du répertoire de travail local au format ZIP et de l'envoyer de manière asynchrone sur votre espace Cloud NEXUS dédié (jusqu'à 100 To de mutualisation) pour sécuriser vos configurations en 1 clic.
*   **Console de Diagnostic & Santé** : Affiche les métriques réelles du serveur (Version PHP, permissions d'écriture du dossier de stockage, extensions `OpenSSL` et `ZipArchive` actives, test de connexion réseau) pour faciliter le support technique.

---

## 🛠️ COMPORTEMENT DE L'ONBOARDING ÉTHIQUE

*   **Redirection automatique** : Dès que l'extension est activée, un aiguillage sécurisé redirige proprement l'utilisateur vers l'onglet de Licence (Iframe d'authentification).
*   **Modale de Bienvenue (Incitation Positive)** : Une modale chaleureuse et unique s'ouvre pour rassurer l'utilisateur sur le mode gratuit (Mega Free) et lui expliquer la valeur de la connexion Cloud pour sécuriser son travail sans frais.
*   **Désactivation d'Adieu Bienveillante (Gentle Goodbye)** : En cas de désactivation du plugin, aucun questionnaire intrusif ne vient importuner l'utilisateur. Une modale éthique l'avertit de la perte de ses fichiers locaux (s'ils ne sont pas sauvegardés dans son Cloud NEXUS) et lui souhaite un prompt retour.
