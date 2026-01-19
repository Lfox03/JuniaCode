---
title: C++
description: Révisez avec les FlashCards sur le C++
---

# Flashcards : Révision C++

Utilisez ces cartes pour tester vos connaissances. Cliquez sur chaque question pour voir la réponse.

---

##  Niveau Débutant

??? question "À quoi sert la ligne `#include <iostream>` ?"
    C'est une directive de préprocesseur qui permet d'inclure la bibliothèque standard d'entrée et de sortie. Elle est indispensable pour utiliser `std::cout` et `std::cin`.

??? question "Quelle est la différence entre `int` et `double` ?"
    - **`int`** : Utilisé pour stocker des nombres **entiers** (ex: 1, -5, 42).
    - **`double`** : Utilisé pour stocker des nombres **à virgule** (ex: 3.14, -0.5).

??? question "Que signifie le `std::` devant `cout` ?"
    `std` est l'abréviation de **Standard**. C'est un **espace de noms** (namespace). Cela indique au compilateur que `cout` appartient à la bibliothèque standard du C++.

---

##  Logique et Boucles

??? question "Quelle est la différence entre une boucle `for` et une boucle `while` ?"
    - On utilise **`for`** quand on connaît à l'avance le nombre d'itérations (ex: répéter 10 fois).
    - On utilise **`while`** quand on veut répéter une action tant qu'une condition est vraie, sans forcément savoir combien de temps cela durera.

??? question "À quoi sert l'opérateur modulo `%` ?"
    Il donne le **reste** d'une division entière. 
    *Exemple : `7 % 2` donne `1` (car 7 = 3 * 2 + **1**).*

??? question "Comment écrit-on la condition "est égal à" dans un `if` ?"
    On utilise le double égal **`==`**. 
    *Attention : un seul `=` sert à l'assignation d'une valeur à une variable.*

---

##  Fonctions et Structure

??? question "Qu'est-ce qu'une fonction `void` ?"
    C'est une fonction qui effectue une action mais **ne renvoie aucune valeur** (pas de `return`).

??? question "Pourquoi le programme commence-t-il toujours par `int main()` ?"
    `main()` est le **point d'entrée** officiel de tout programme C++. C'est la première fonction exécutée par l'ordinateur au lancement.

??? question "À quoi sert `std::endl` ?"
    Il permet deux choses :
    1. Aller à la ligne suivante dans la console.
    2. "Vider le tampon" (flush), ce qui force l'affichage immédiat du texte à l'écran.

---

##  Syntaxe et Erreurs

??? question "Qu'arrive-t-il si on oublie un `;` à la fin d'une ligne ?"
    Le programme ne pourra pas être compilé. Le compilateur générera une **erreur de syntaxe**.

??? question "Comment déclare-t-on une constante (une variable qui ne change jamais) ?"
    On utilise le mot-clé **`const`** avant le type.
    *Exemple : `const double PI = 3.14159;`*

---

!!! tip "Conseil de révision"
    Révisez 
    
    ![jad](../../assets/jad.png){ width="150" } 