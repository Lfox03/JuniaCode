---
title: Arduino
description: Révisez avec les FlashCards Arduino
---

# Flashcards : Révision Arduino

Utilisez ces cartes pour tester vos connaissances. Cliquez sur chaque question pour voir la réponse.

---

##  Bases de l’Arduino

??? question "Qu’est-ce qu’une carte Arduino ?"
    Une carte Arduino est une carte électronique programmable basée sur un microcontrôleur, utilisée pour prototyper des systèmes électroniques et embarqués.

??? question "Quel est le rôle principal du microcontrôleur ?"
    Exécuter un programme stocké en mémoire pour lire des entrées, traiter des données et piloter des sorties.

??? question "Quels sont les deux types principaux de broches Arduino ?"
    Les broches numériques (digital) et les broches analogiques.

??? question "À quoi sert la broche GND ?"
    Elle correspond à la masse (0 V) et sert de référence électrique pour tout le circuit.

??? question "À quoi sert la broche 5V ?"
    Elle fournit une tension de 5 volts pour alimenter des composants externes.

---

##  Programmation Arduino

??? question "Quelle est la structure minimale d’un programme Arduino ?"
    Deux fonctions obligatoires : `setup()` et `loop()`.

??? question "À quoi sert la fonction setup() ?"
    Elle est exécutée une seule fois au démarrage pour initialiser les paramètres et les broches.

??? question "À quoi sert la fonction loop() ?"
    Elle s’exécute en boucle infinie tant que la carte est alimentée.

??? question "Quelle instruction permet de configurer une broche en entrée ou en sortie ?"
    `pinMode(broche, mode)` avec `INPUT`, `OUTPUT` ou `INPUT_PULLUP`.

??? question "Quelle instruction permet d’écrire un état logique sur une broche ?"
    `digitalWrite(broche, HIGH)` ou `digitalWrite(broche, LOW)`.

---

##  Entrées / Sorties

??? question "Quelle fonction permet de lire une entrée numérique ?"
    `digitalRead(broche)`.

??? question "Quelle fonction permet de lire une entrée analogique ?"
    `analogRead(broche)`.

??? question "Quelle est la plage de valeurs renvoyées par analogRead() ?"
    De 0 à 1023 (sur Arduino Uno, résolution 10 bits).

??? question "Quelle fonction permet de générer un signal PWM ?"
    `analogWrite(broche, valeur)`.

??? question "Sur quelles valeurs agit analogWrite() ?"
    Sur une valeur comprise entre 0 et 255 (rapport cyclique PWM).

---

##  Temps et temporisation

??? question "Quelle fonction permet de faire une pause dans le programme ?"
    `delay(ms)`.

??? question "En quelle unité est exprimé le paramètre de delay() ?"
    En millisecondes.

??? question "Quelle fonction permet de connaître le temps écoulé depuis le démarrage ?"
    `millis()`.

??? question "Pourquoi éviter delay() dans des programmes complexes ?"
    Parce qu’elle bloque l’exécution et empêche de gérer plusieurs tâches en parallèle.

---

## Communication série

??? question "Quelle fonction initialise la communication série ?"
    `Serial.begin(vitesse)`.

??? question "Quelle vitesse est la plus couramment utilisée ?"
    9600 bauds.

??? question "Quelle fonction permet d’envoyer un message vers le moniteur série ?"
    `Serial.print()` ou `Serial.println()`.

??? question "Quelle fonction permet de lire une donnée reçue sur le port série ?"
    `Serial.read()`.

??? question "À quoi sert le moniteur série ?"
    À afficher des messages et déboguer le programme.

---

## Capteurs et actionneurs

??? question "Qu’est-ce qu’un capteur ?"
    Un composant qui transforme une grandeur physique en signal électrique.

??? question "Qu’est-ce qu’un actionneur ?"
    Un composant qui transforme un signal électrique en action mécanique ou lumineuse.

??? question "Donne un exemple de capteur utilisé avec Arduino."
    Capteur de température, capteur de luminosité (LDR), bouton poussoir.

??? question "Donne un exemple d’actionneur utilisé avec Arduino."
    LED, moteur, servo, buzzer.

---

## Bonnes pratiques

??? question "Pourquoi utiliser des résistances avec des LED ?"
    Pour limiter le courant et éviter de détruire la LED.

??? question "Pourquoi relier toutes les masses ensemble ?"
    Pour avoir une référence commune de tension.

??? question "Pourquoi commenter son code ?"
    Pour améliorer la lisibilité et faciliter la maintenance.

??? question "Pourquoi tester progressivement un montage ?"
    Pour localiser plus facilement les erreurs matérielles ou logicielles.

---

!!! tip "Conseil de révision"
    Révisez 
    
    ![jad](../../assets/jad.png){ width="150" } 