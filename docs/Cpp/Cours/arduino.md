---
title: Arduino
description: Les bases en Arduino
icon: simple/arduino
tags:
  - révision
  - syntaxe
  - automatismes
  - électronique
  - pratique
---

## **Arduino : _Kesako_ ?**

Avant de plonger dans le monde d'Arduino, il est important de comprendre comment cette plateforme se distingue du **C++ traditionnel**.

### Qu'est-ce qu'Arduino ?

Arduino est une plateforme open-source conçue pour la prototypage rapide et l'apprentissage de l'électronique. Elle utilise une version simplifiée du C++, mais avec des bibliothèques spécifiques pour interagir avec le matériel.

!!! warning "Attention"
  
    Arduino n'est **pas un langage de programmation**, mais bien un **environnement de développement** qui permet de programmer des microcontroleurs compatibles.

#### Comparaison rapide

| **Critère**               | **C++ traditionnel**                          | **Arduino**                                  |
|--------------------------|-----------------------------------------------|---------------------------------------------|
| **Utilisation**           | Applications logicielles, systèmes embarqués   | Prototypage électronique, projets DIY        |
| **Gestion mémoire**       | Manuelle (risque de fuites)                   | Simplifiée (moins critique)                 |
| **Bibliothèques**         | Standard (STL)                               | Spécifiques (broches, capteurs, etc.)       |
| **Compilation**           | `g++`, `clang`                                | IDE Arduino (simplifié)                     |
| **Cible**                 | PC, serveurs, systèmes complexes              | Microcontrôleurs (ex: ATmega328P)           |

### Exemples comparatifs

#### C++ traditionnel
```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
```

#### Arduino
```cpp
void setup() {
  Serial.begin(9600);
}

void loop() {
  Serial.println("Hello World!");
  delay(1000);
}
```

### Pourquoi choisir Arduino ?

**✅ Avantages :**

- **Simplicité** : Idéal pour les débutants.

- **Bibliothèques matérielles** : Facilite l'interaction avec les capteurs et actionneurs.

- **Communauté active** : Nombreux tutoriels et projets partagés.

**❌ Inconvénients :**

- **Limitations matérielles** : Moins adapté aux applications complexes.

- **IDE moins flexible** : Moins puissant que des outils comme VS Code ou CLion.


**À retenir :**

Arduino est une **version simplifiée du C++**, optimisée pour l'électronique. On y retrouve les concepts de base (boucles, conditions), mais avec un focus sur le matériel.

---

## **1. Les structures incontournables à maîtriser**

### **A. Structure de base d'un programme Arduino**
```cpp
void setup() {
  // Code exécuté une seule fois au démarrage
}

void loop() {
  // Code exécuté en boucle indéfiniment
}
```

!!! note "À retenir"
    
     - `setup()` = Initialisation (broches, variables)
    
     - `loop()` = Comportement répétitif

### **B. Gestion des broches**

| Type de broche | Fonction | Exemple |
|----------------|----------|---------|
| Entrée numérique | Lire un état (HIGH/LOW) | `int etatBouton = digitalRead(boutonPin);` |
| Sortie numérique | Contrôler une LED | `digitalWrite(ledPin, HIGH);` |
| PWM | Contrôle de vitesse/moteur | `analogWrite(pwmPin, 128);` |

!!! tip "Astuce mémoire"
    
    - Associez toujours `digital` à `HIGH/LOW`
    
    - `PWM` implique toujours un nombre entre 0 et 255

---

## **2. Méthode d'entraînement par l'exemple**

### **Cas pratique : Machine à sous simplifiée**
**Problème** :
Créer une machine à sous avec :

- 3 LEDs (broches 13, 12, 11)

- 1 bouton (boutonPin = 8)

- Afficher une séquence aléatoire de 3 LEDs

```cpp linenums="1"
#include <Arduino.h>

const int ledPins[] = {13, 12, 11};
const int boutonPin = 8;
int etatBouton;

void setup() {
  // Initialisation des broches
  for (int i = 0; i < 3; i++) {
    pinMode(ledPins[i], OUTPUT);
  }
  pinMode(boutonPin, INPUT_PULLUP); // Résistance interne
}

void loop() {
  etatBouton = digitalRead(boutonPin);

  if (etatBouton == LOW) { // Bouton enfoncé
    afficherSequence();
    delay(1000);
  }
}

void afficherSequence() {
  for (int i = 0; i < 3; i++) {
    digitalWrite(ledPins[i], HIGH);
    delay(200);
    digitalWrite(ledPins[i], LOW);
  }
}
```

!!! info "Analyse syntaxique"
    
    - `INPUT_PULLUP` : Évite le branchement d'une résistance externe
    
    - `for()` imbriqué : Pour les séquences répétitives
    
    - Fonction `afficherSequence()` : Modularité du code

---

## **Tableau de révision rapide**

| Structure | Syntaxe | Cas d'usage |
|-----------|---------|-------------|
| `pinMode()` | `pinMode(pin, MODE)` | Configurer une broche |
| `digitalWrite()` | `digitalWrite(pin, ETAT)` | Contrôler une sortie |
| `delay()` | `delay(ms)` | Attendre un temps |
| `if` | `if (condition) {}` | Prise de décision |
| `for` | `for (int i=0; i<n; i++) {}` | Boucles répétitives |

---

## **Exercice d'application**

> vu avec JAD :custom-jad:

Compléter le code suivant pour qu'une LED clignote en morse "SOS" (• • • — — — • • •) quand un bouton est pressé.

```cpp
const int ledPin = 13;
const int boutonPin = 8;

void setup() {
  // À compléter : configuration des broches
}

void loop() {
  if (/* Condition à compléter */) {
    // Séquence SOS
    for (int i = 0; i < 3; i++) {
      digitalWrite(ledPin, HIGH);
      delay(200); // Durée d'un point
      digitalWrite(ledPin, LOW);
      delay(100); // Pause entre points
    }
    // À compléter : pause entre lettres
    for (int i = 0; i < 3; i++) {
      /* Code pour un trait */
    }
    // À compléter : pause finale
  }
}
```

??? success "Corrigé"

    ```cpp
    void setup() {
      pinMode(ledPin, OUTPUT);
      pinMode(boutonPin, INPUT_PULLUP);
    }

    void loop() {
      if (digitalRead(boutonPin) == LOW) {
        // Séquence SOS
        for (int i = 0; i < 3; i++) {
          digitalWrite(ledPin, HIGH);
          delay(200); // Durée d'un point
          digitalWrite(ledPin, LOW);
          delay(100); // Pause entre points
        }
        delay(300); // Pause entre lettres (trait)
        for (int i = 0; i < 3; i++) {
          digitalWrite(ledPin, HIGH);
          delay(600); // Durée d'un trait
          digitalWrite(ledPin, LOW);
          delay(100); // Pause entre traits
        }
        delay(700); // Pause finale
      }
    }
    ```

---

## **Ressources Utiles**

| Ressource | Description |
|-----------|-------------|
| [📖 Documentation officielle](https://www.arduino.cc/en/Reference/HomePage) | Tout savoir sur les fonctions Arduino. |
| [🛠️ Simulateur en ligne (Tinkercad)](https://www.tinkercad.com/) | Teste tes circuits sans matériel ! |
| [📌 Flashcards : Broches Arduino](../FlashCard/index.md) | Révise les broches importantes. |