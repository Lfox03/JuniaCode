---
title: débutants
description: Les bases en C++
icon: material/star
weight: 0
---

# Exercices débutants

Mettez en pratique vos connaissances sur les variables, les conditions, les boucles et les fonctions.

---

## Exercice 1 : Le Calculateur d'Aire

**Objectif :** Manipuler les variables et les entrées/sorties (`cin`/`cout`).

Écrivez un programme qui demande à l'utilisateur la **largeur** et la **longueur** d'un rectangle (nombres à virgule), puis affiche l'aire.

??? success "Correction"
    ```cpp
    #include <iostream>

    int main() {
        double largeur, longueur;

        std::cout << "Entrez la largeur : ";
        std::cin >> largeur;
        std::cout << "Entrez la longueur : ";
        std::cin >> longueur;

        double aire = largeur * longueur;
        std::cout << "L'aire du rectangle est : " << aire << std::endl;

        return 0;
    }
    ```

---

## Exercice 2 : Pair ou Impair ?

**Objectif :** Utiliser les structures conditionnelles (`if` / `else`) et l'opérateur modulo `%`.

Demandez un nombre entier à l'utilisateur et affichez s'il est **Pair** ou **Impair**.

!!! info "Indice"
    Un nombre est pair si le reste de sa division par 2 est égal à 0 (utilisation de `% 2`).

??? success "Correction"
    ```cpp
    #include <iostream>

    int main() {
        int nombre;
        std::cout << "Entrez un nombre entier : ";
        std::cin >> nombre;

        if (nombre % 2 == 0) {
            std::cout << "Le nombre est Pair." << std::endl;
        } else {
            std::cout << "Le nombre est Impair." << std::endl;
        }

        return 0;
    }
    ```

---

## Exercice 3 : La Table de Multiplication

**Objectif :** Utiliser une boucle `for`.

Demandez un nombre à l'utilisateur (ex: 7) et affichez sa table de multiplication de 1 à 10.
*Exemple de sortie : 7 x 1 = 7, 7 x 2 = 14, etc.*

??? success "Correction"
    ```cpp
    #include <iostream>

    int main() {
        int n;
        std::cout << "Quelle table voulez-vous voir ? ";
        std::cin >> n;

        for (int i = 1; i <= 10; i++) {
            std::cout << n << " x " << i << " = " << n * i << std::endl;
        }

        return 0;
    }
    ```

---

## Exercice 4 : Conversion de Température (Fonction)

**Objectif :** Créer et appeler une fonction.

Créez une fonction nommée `celsiusVersFahrenheit` qui prend un `double` (Celsius) en paramètre et retourne la conversion en Fahrenheit.
*Formule : Fahrenheit = (Celsius * 9/5) + 32*

Dans le `main`, demandez une température à l'utilisateur et affichez le résultat converti.

??? success "Correction"
    ```cpp
    #include <iostream>

    // Définition de la fonction de conversion
    double celsiusVersFahrenheit(double celsius) {
        return (celsius * 9.0 / 5.0) + 32.0;
    }

    int main() {
        double tempC;
        std::cout << "Entrez la temperature en Celsius : ";
        std::cin >> tempC;

        double tempF = celsiusVersFahrenheit(tempC);
        std::cout << tempC << "C correspond a " << tempF << "F" << std::endl;

        return 0;
    }
    ```

---

## Exercice 5 : Le Juste Prix (Mini-projet)

**Objectif :** Combiner boucles et conditions.

Le programme choisit un nombre secret (disons 42). Tant que l'utilisateur n'a pas trouvé le nombre, le programme lui demande une proposition et lui répond "C'est plus !" ou "C'est moins !".

??? success "Correction"
    ```cpp
    #include <iostream>

    int main() {
        int nombreSecret = 42;
        int essai = 0;

        std::cout << "--- Bienvenue au Juste Prix ---" << std::endl;

        while (essai != nombreSecret) {
            std::cout << "Devinez le nombre : ";
            std::cin >> essai;

            if (essai < nombreSecret) {
                std::cout << "C'est plus !" << std::endl;
            } else if (essai > nombreSecret) {
                std::cout << "C'est moins !" << std::endl;
            }
        }

        std::cout << "Bravo ! Vous avez gagne." << std::endl;
        return 0;
    }
    ```