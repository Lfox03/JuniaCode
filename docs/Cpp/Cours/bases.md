---
title: Les bases
description: Les bases en C++
icon: material/code-braces
---

# Les bases en C++

Bienvenue dans ce cours d'introduction au C++. Le C++ est un langage puissant, performant et largement utilisé dans l'industrie (jeux vidéo, systèmes embarqués, finance).

!!! info "Attention"

    Il s'agit ici d'un cours C++, et non d'Arduino. 

## 1. Votre premier programme

Tout apprentissage commence par le traditionnel "Hello World". Ce code affiche un message à l'écran.

```cpp
#include <iostream> // (1)

int main() { // (2)
    std::cout << "Bonjour tout le monde !" << std::endl; // (3)
    return 0; // (4)
}
```

1.  **#include <iostream>** : Inclut la bibliothèque standard d'entrée/sortie.
2.  **int main()** : Point d'entrée obligatoire de tout programme C++.
3.  **std::cout** : "Character Output" (affiche du texte). `std::endl` crée un retour à la ligne.
4.  **return 0** : Indique au système que le programme s'est terminé sans erreur.


---

## 2. Variables et Types de base

En C++, vous devez déclarer le **type** d'une variable avant de l'utiliser.

| Type | Description | Exemple |
| :--- | :--- | :--- |
| `int` | Nombres entiers | `int age = 25;` |
| `double` | Nombres à virgule | `double prix = 19.99;` |
| `char` | Un seul caractère | `char lettre = 'A';` |
| `bool` | Vrai ou Faux | `bool estPrêt = true;` |
| `std::string` | Chaîne de caractères | `std::string nom = "Alice";` |

!!! info "Important"
    N'oubliez jamais le **point-virgule** `;` à la fin de chaque instruction ! C'est l'erreur la plus fréquente chez les débutants.

---

## 3. Interagir avec l'utilisateur

Pour récupérer une information saisie au clavier, on utilise `std::cin`.

```cpp
#include <iostream>
#include <string>

int main() {
    int age;
    std::cout << "Quel est votre âge ? ";
    std::cin >> age; // On stocke la saisie dans la variable age

    std::cout << "Vous avez " << age << " ans." << std::endl;
    return 0;
}
```

---

## 4. Les Structures Conditionnelles

Pour prendre des décisions, on utilise `if`, `else if` et `else`.

```cpp
int score = 85;

if (score >= 90) {
    std::cout << "Excellent !" << std::endl;
} else if (score >= 50) {
    std::cout << "C'est réussi." << std::endl;
} else {
    std::cout << "C'est un échec." << std::endl;
}
```

---

## 5. Compilation et Exécution

Le C++ est un langage **compilé**. Vous devez transformer votre texte en un fichier exécutable.

=== "Sous Linux / macOS"
    ```bash
    g++ main.cpp -o mon_programme
    ./mon_programme
    ```

=== "Sous Windows"
    Utilisez un IDE comme **Visual Studio** ou **Code::Blocks**, ou utilisez la commande suivante si vous avez `MinGW` :
    ```bash
    g++ main.cpp -o mon_programme.exe
    mon_programme.exe
    ```

---

!!! success "Félicitations !"
    Vous venez de voir les bases fondamentales. La prochaine étape logique est l'apprentissage des **boucles** (`for`, `while`) et des **fonctions**.

# Boucles et Fonctions en C++

Maintenant que vous savez manipuler des variables et des conditions, passons à l'automatisation avec les boucles et à l'organisation avec les fonctions.

---

## 1. Les Boucles (Loops)

Les boucles permettent de répéter un bloc d'instructions plusieurs fois.

### La boucle `for`
Idéale quand on connaît à l'avance le nombre de répétitions.

```cpp
// Affiche les nombres de 1 à 5
for (int i = 1; i <= 5; i++) {
    std::cout << "Iteration : " << i << std::endl;
}
```

### La boucle `while`
Idéale quand on veut répéter une action tant qu'une condition est vraie.

```cpp
int stock = 3;
while (stock > 0) {
    std::cout << "Vente effectuée. Stock restant : " << stock << std::endl;
    stock--; // On diminue le stock
}
```

!!! warning "Attention"
    Veillez à ce que la condition de votre boucle `while` devienne fausse à un moment donné, sinon vous créerez une **boucle infinie** qui fera planter votre programme !

---

## 2. Les Fonctions

Une fonction est un bloc de code réutilisable. Elle permet d'éviter la répétition et de rendre le code plus lisible.

### Structure d'une fonction
Une fonction possède un **type de retour**, un **nom**, et parfois des **paramètres**.

```cpp
// Cette fonction prend deux entiers et retourne leur somme
int additionner(int a, int b) {
    return a + b;
}

// Fonction "void" : elle ne retourne rien, elle fait juste une action
void direBonjour(std::string nom) {
    std::cout << "Bonjour " << nom << " !" << std::endl;
}
```

### Utilisation dans le programme
Voici comment on assemble le tout :

```cpp
#include <iostream>
#include <string>

// Déclaration de la fonction
int calculerCarre(int nombre) {
    return nombre * nombre;
}

int main() {
    int valeur = 5;
    int resultat = calculerCarre(valeur); // Appel de la fonction

    std::cout << "Le carre de " << valeur << " est " << resultat << std::endl;
    
    return 0;
}
```

---

## 3. Exemple Récapitulatif

Voici un petit programme qui combine boucles, conditions et fonctions :

```cpp
#include <iostream>

bool estPair(int n) {
    return (n % 2 == 0);
}

int main() {
    int limite;
    std::cout << "Jusqu'à quel nombre voulez-vous tester ? ";
    std::cin >> limite;

    for (int i = 1; i <= limite; i++) {
        if (estPair(i)) {
            std::cout << i << " est PAIR" << std::endl;
        } else {
            std::cout << i << " est IMPAIR" << std::endl;
        }
    }

    return 0;
}
```

---

## 4. Organisation du code (MkDocs Tips)

Dans un projet C++ réel, on sépare souvent le code en plusieurs fichiers. Dans votre documentation MkDocs, vous pouvez utiliser les onglets pour montrer cette séparation :

=== "main.cpp"
    ```cpp
    #include "outils.hpp"
    int main() {
        saluer();
        return 0;
    }
    ```

=== "outils.hpp"
    ```cpp
    #include <iostream>
    void saluer() {
        std::cout << "Salut depuis le header !" << std::endl;
    }
    ```

!!! note "À retenir"
    Le C++ lit le code de haut en bas. Si vous utilisez une fonction dans le `main()`, elle doit être définie **au-dessus** du `main()` ou déclarée via un prototype.

---

!!! success "Étape franchie !"
    Vous maîtrisez maintenant les bases de l'algorithmique en C++. La prochaine grande étape est l'**Orienté Objet (Classes et Objets)**.