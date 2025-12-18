# 🎓 MATHBAC - L'Outil Ultime pour le Bac

![Flutter](https://img.shields.io/badge/Flutter-3.0%2B-02569B?logo=flutter)
![Dart](https://img.shields.io/badge/Dart-3.0%2B-0175C2?logo=dart)
![Platform](https://img.shields.io/badge/Platform-Android%20%7C%20iOS-orange)
![License](https://img.shields.io/badge/License-Proprietary-red)

**MATHBAC** est une application mobile complète développée en **Flutter** pour accompagner les lycéens de Terminale dans leur préparation au Baccalauréat de Mathématiques. Elle couvre les trois parcours principaux : **Spécialité Maths**, **Maths Expertes** et **Maths Complémentaires**.

L'application combine des ressources pédagogiques (cours, annales) et des outils techniques avancés (traceur de fonctions, calculatrice) dans une interface moderne et intuitive.

---

## 📱 Aperçu de l'application

| Accueil | Choix Parcours | Traceur | Annales |
|:---:|:---:|:---:|:---:|
| <img src="images/screen1.jpg" width="200" /> | <img src="images/screen2.jpg" width="200" /> | <img src="images/screen3.jpg" width="200" /> | <img src="images/screen4.jpg" width="200" /> |

---

## 🚀 Fonctionnalités Clés

### 📚 Pédagogie & Révisions
* **Contenu Structuré :** Chargement dynamique des cours via des fichiers JSON locaux, filtrés par matière (Analyse, Géométrie, Probas, etc.).
* **Fiches de Cours :** Affichage clair avec formatage riche pour une lecture facile sur mobile.
* **Formulaires :** Accès rapide aux formules essentielles classées par chapitre.
* **Annales du Bac :** Liste des sujets d'examens récents avec distinction visuelle pour les années > 2023.

### 🛠️ Outils Mathématiques Intégrés
* **Traceur de Fonctions Interactif :**
    * Utilisation de la librairie `fl_chart` et `math_expressions`.
    * Calcul automatique des racines, minimums/maximums et de l'intégrale.
    * Gestion du zoom et du déplacement tactile.
* **Calculatrice Scientifique :**
    * Support des unités d'angle (Degrés, Radians, Grades).
    * Historique des calculs sauvegardé localement (Persistance des données via `SharedPreferences`).

### 💎 Modèle Freemium & Monétisation
* **Système Premium :** Intégration de `in_app_purchase` pour débloquer le "Pack Réussite".
* **Contenu Verrouillé :** Les corrigés détaillés et certaines fonctionnalités avancées sont floutés pour les utilisateurs gratuits.
* **Paywall :** Interface de vente incitative moderne.

---

## 🛠️ Stack Technique

* **Framework :** [Flutter](https://flutter.dev/)
* **Langage :** [Dart](https://dart.dev/)
* **Gestion des Données :** JSON (Assets locaux)
* **Persistance :** `shared_preferences` (Historiques calculatrice/traceur, statut Premium)
* **Graphiques :** `fl_chart`
* **Calculs Mathématiques :** `math_expressions`
* **Achats In-App :** `in_app_purchase`
* **Polices :** `google_fonts` (Poppins)

---

## 📂 Structure du Projet

L'architecture suit une séparation claire entre l'interface (UI), la logique (Services) et les données.

```text
lib/
├── main.dart                 # Point d'entrée, Thème, Routes
├── pages/
│   ├── home_page.dart        # Dashboard principal (Design "Curved")
│   ├── subject_selection.dart# Page de choix (Spé/Expertes/Comp)
│   ├── courses_page.dart     # Liste des chapitres
│   ├── calculator_page.dart  # Calculatrice scientifique
│   ├── tracer_page.dart      # Traceur de fonctions
│   └── ...
├── services/
│   ├── data_service.dart     # Chargeur de JSON (Cours, Exos)
│   └── payment_service.dart  # Gestion des achats In-App
├── widgets/
│   ├── draggable_menu.dart   # Menu flottant (Calculatrice/Traceur)
│   └── ...
assets/
└── data/                     # Fichiers JSON (cours.json, exercices.json...)