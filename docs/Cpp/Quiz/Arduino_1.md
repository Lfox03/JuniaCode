---
title: Arduino
description: Quiz sur Arduino
quiz:
  shuffle_answers: true
---

# Quiz sur Arduino

Voici un quiz de **15 questions** sur **Arduino**

!!! info ""
    <!-- mkdocs-quiz intro -->

<quiz>
À quoi sert principalement une carte Arduino ?
- [x] À exécuter des programmes pour contrôler des composants électroniques
- [ ] À afficher des pages web
- [ ] À stocker des fichiers multimédias
- [ ] À remplacer un ordinateur

Une carte Arduino sert surtout à piloter des capteurs et des actionneurs via un microcontrôleur.
</quiz>

<quiz>
Quelles sont les deux fonctions obligatoires dans un programme Arduino ?
- [x] setup()
- [x] loop()
- [ ] main()
- [ ] start()

setup() s’exécute une fois au démarrage, loop() tourne en boucle.
</quiz>

<quiz>
Quelle instruction permet de configurer une broche en sortie ?
- [x] pinMode(broche, OUTPUT)
- [ ] digitalWrite(broche, OUTPUT)
- [ ] analogWrite(broche, OUTPUT)
- [ ] setPin(broche, OUTPUT)

pinMode sert à définir le mode d’une broche.
</quiz>

<quiz>
Quelle fonction permet d’écrire un état logique sur une broche numérique ?
- [x] digitalWrite()
- [ ] digitalRead()
- [ ] analogWrite()
- [ ] pinMode()

digitalWrite permet d’envoyer HIGH ou LOW sur une broche.
</quiz>

<quiz>
Quelle fonction permet de lire une entrée numérique ?
- [x] digitalRead()
- [ ] digitalWrite()
- [ ] analogRead()
- [ ] readPin()

digitalRead lit l’état HIGH ou LOW d’une broche.
</quiz>

<quiz>
Quelle est la plage de valeurs retournée par analogRead() sur Arduino Uno ?
- [x] De 0 à 1023
- [ ] De 0 à 255
- [ ] De -1023 à 1023
- [ ] De 0 à 5

analogRead renvoie une valeur sur 10 bits, donc entre 0 et 1023.
</quiz>

<quiz>
Quelle instruction permet de générer un signal PWM ?
- [x] analogWrite()
- [ ] digitalWrite()
- [ ] pwmWrite()
- [ ] tone()

analogWrite permet de simuler une tension variable par PWM.
</quiz>

<quiz>
Quel est le rôle de la fonction delay() ?
- [x] Mettre le programme en pause pendant un certain temps
- [ ] Réinitialiser la carte
- [ ] Lire un capteur
- [ ] Arrêter définitivement le programme

delay bloque l’exécution pendant un nombre de millisecondes donné.
</quiz>

<quiz>
Quelle fonction permet de connaître le temps écoulé depuis le démarrage de la carte ?
- [x] millis()
- [ ] delay()
- [ ] time()
- [ ] clock()

millis renvoie le nombre de millisecondes depuis le démarrage.
</quiz>

<quiz>
Quelle instruction initialise la communication série ?
- [x] Serial.begin()
- [ ] Serial.start()
- [ ] Serial.open()
- [ ] Serial.init()

Serial.begin configure la vitesse de transmission.
</quiz>

<quiz>
Quelle vitesse est la plus couramment utilisée pour le port série ?
- [x] 9600
- [ ] 4800
- [ ] 115200
- [ ] 300

9600 bauds est la valeur la plus utilisée en début de projet.
</quiz>

<quiz>
À quoi sert la broche GND ?
- [x] À fournir la masse (0 V)
- [ ] À fournir 5 V
- [ ] À transmettre des données
- [ ] À programmer la carte

Toutes les tensions sont mesurées par rapport à GND.
</quiz>

<quiz>
Pourquoi faut-il utiliser une résistance avec une LED ?
- [x] Pour limiter le courant et éviter de la détruire
- [ ] Pour augmenter la luminosité
- [ ] Pour inverser la polarité
- [ ] Pour accélérer la LED

Sans résistance, la LED peut griller très rapidement.
</quiz>

<quiz>
Qu’est-ce qu’un capteur ?
- [x] Un composant qui mesure une grandeur physique
- [ ] Un composant qui affiche des données
- [ ] Un composant qui stocke de l’énergie
- [ ] Un composant qui programme la carte

Un capteur transforme une grandeur physique en signal électrique.
</quiz>

<quiz>
Qu’est-ce qu’un actionneur ?
- [x] Un composant qui agit sur l’environnement
- [ ] Un composant qui mesure une tension
- [ ] Un composant qui stocke un programme
- [ ] Un composant qui communique avec Internet

Un moteur, une LED ou un buzzer sont des actionneurs.
</quiz>

<!-- mkdocs-quiz results -->