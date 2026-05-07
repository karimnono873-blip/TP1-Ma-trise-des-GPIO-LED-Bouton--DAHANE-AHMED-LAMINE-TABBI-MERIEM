# TP 1 : Maîtrise des GPIO - Systèmes Embarqués

Ce dépôt contient les codes sources et le compte-rendu interactif du TP1 sur la configuration et la manipulation des GPIO avec la carte **STM32 Nucleo-C031C6**.

## 🚀 Description du Projet

L'objectif de ces travaux pratiques est d'appréhender la programmation matérielle d'un microcontrôleur STM32 en utilisant la bibliothèque HAL. Le projet illustre l'évolution d'un simple contrôle d'E/S (allumer une LED via un bouton) jusqu'à la conception d'une architecture logicielle plus robuste (machine à états non-bloquante) pour gérer des événements asynchrones sans figer le processeur.

## 📋 Manipulations Réalisées

1. **Application de base :** Contrôle direct. Allumage d'une LED externe (PA5) uniquement lorsque le bouton utilisateur (PC13) est physiquement maintenu enfoncé, illustrant la lecture d'état logique et la gestion des résistances de tirage (Pull-up).
2. **Test Toggle :** Clignotement continu avec une période de 500ms en utilisant la fonction `HAL_GPIO_TogglePin()`.
3. **Le Défi (Variateur de Vitesse) :** Changement dynamique de la vitesse de clignotement (Lent: 1000ms, Rapide: 200ms, Fixe) à chaque appui sur le bouton. Implémenté de niveau "Pro" sans utiliser `HAL_Delay()`, mais via `HAL_GetTick()` pour garantir une détection instantanée des appuis (anti-rebond logiciel inclus).

## 🛠️ Matériel Requis

* Carte STM32 Nucleo-C031C6 (Matériel physique ou simulation via [Wokwi](https://wokwi.com/stm32))
* 1x LED
* 1x Résistance (220Ω - 330Ω)
* Environnement de développement : STM32CubeIDE

## 📁 Structure du Dépôt

* `main.c` : Le code source principal en C contenant la logique (actuellement configuré pour le Défi Variateur de Vitesse).
* `main.h` : Le fichier d'en-tête contenant les directives de préprocesseur et les prototypes.
* `compte_rendu_tp1.html` : Un rapport de laboratoire interactif (thème spatial/cyberpunk) contenant le code de chaque manipulation, les réponses détaillées aux questions Post-Lab, et une visualisation schématique du montage.

## ⚙️ Instructions de Simulation (Wokwi)

1. Ouvrez un nouveau projet STM32 Nucleo64 C031C6 sur Wokwi.
2. Ajoutez une LED et une résistance sur la grille.
3. Connectez l'anode de la LED à la broche **PA5** et la cathode à la résistance, puis à la masse (GND). Le bouton intégré sur **PC13** est utilisé pour les entrées.
4. Remplacez le contenu de `sketch.ino`/`main.c` par le code fourni dans ce dépôt, et assurez-vous que `main.h` est présent.
5. Cliquez sur *Play* pour lancer la simulation.

## 👥 Auteurs

* **Dahane Ahmed Lamine**
* **Tabbi Meriem**
* Enseignante : **Afaf Saoud**
