---
title: C++
description: Quiz sur le C++
quiz:
  shuffle_answers: true
---

# Quiz sur le C++

Voici un quiz de **15 questions** sur le langage **C++**

!!! info ""
    <!-- mkdocs-quiz intro -->

<quiz>
Quel est l'avantage principal d'utiliser des références (`&`) plutôt que des pointeurs (`*`) en C++ ?
- [x] Évite les erreurs de nullité et simplifie la syntaxe
- [ ] Permet de manipuler directement la mémoire brute
- [ ] N'est compatible qu'avec les types primitifs

Les références sont plus sûres (pas de `nullptr`), plus lisibles, et ne peuvent pas être réaffectées.
</quiz>

<quiz>
Quelle est la sortie du programme suivant ?
```cpp
int main() {
    int x = 5;
    const int& ref = x;
    ref = 10;
}
```
- [x] Erreur de compilation
- [ ] Affiche `10`
- [ ] Affiche `5`

Une référence constante ne peut pas modifier la valeur de l'objet référencé.
</quiz>

<quiz>
Comment initialiser un tableau dynamique en C++ ?
```cpp
int* tab = new int[10]{}; // Initialise tous les éléments à 0
```
- [x] Correct, avec `{}` pour l'initialisation
- [ ] Incorrect, il faut utiliser `memset`
- [ ] Incorrect, la syntaxe est `new int[10] = {0}`

La syntaxe `new int[n]{}` initialise tous les éléments à zéro (valeur par défaut).
</quiz>

<quiz>
Quelle est la différence entre `std::vector` et un tableau C (`int[]`) ?
- [x] Le `vector` gère dynamiquement sa taille et évite les fuites mémoire
- [ ] Un tableau C est plus rapide en accès aléatoire
- [ ] Les deux nécessitent une allocation manuelle avec `new`

Le `vector` est plus sûr (pas de `delete` nécessaire) et redimensionnable.
</quiz>

<quiz>
Pourquoi utiliser `std::unique_ptr` plutôt qu'un pointeur brut (`int*`) ?
```cpp
auto ptr = std::make_unique<int>(42);
```
- [x] Gère automatiquement la mémoire
- [ ] Permet plusieurs copies du même pointeur
- [ ] Est plus lent que les pointeurs bruts

`unique_ptr` implémente l'ownership unique et libère la mémoire automatiquement.
</quiz>

<quiz>
Quelle est la sortie de ce code ?
```cpp
int main() {
    int a = 5;
    int& b = a;
    const int& c = b;
    std::cout << (c == a); // Affiche quoi ?
}
```
- [x] `1`
- [ ] `0`
- [ ] Erreur de compilation

Les références ne créent pas de copies, donc `c` et `a` sont identiques.
</quiz>

<quiz>
Comment éviter les fuites mémoire avec un tableau dynamique ?

- [x] Utiliser `delete[]`
- [ ] Utiliser `free(tab)`
- [ ] Le compilateur le fait automatiquement

`new[]` nécessite `delete[]` pour éviter les fuites.

```cpp
int* tab = new int[10];
delete[] tab;
```
</quiz>

<quiz>
Quelle est la différence entre `std::shared_ptr` et `std::weak_ptr` ?
- [x] `weak_ptr` ne peut pas être utilisé pour accéder à l'objet
- [ ] `shared_ptr` est plus lent que `weak_ptr`
- [ ] Ils font la même chose

`weak_ptr` permet de briser les cycles de références sans posséder l'objet.
</quiz>

<quiz>
Pourquoi ce code ne compile-t-il pas ?
```cpp
int main() {
    int x = 5;
    const int& ref = x;
    ref = 10;
}
```
- [x] `ref` est une référence constante
- [ ] C'est une erreur de syntaxe
- [ ] Le compilateur ignore les références constantes

Une référence constante ne permet pas de modifier l'objet référencé.
</quiz>

<quiz>
Comment initialiser un `std::array` en C++ ?
```cpp
std::array<int, 5> arr = {1, 2, 3}; // Le reste est initialisé à 0
```
- [x] Correct
- [ ] Incorrect, il faut tous les initialiser explicitement
- [ ] Incorrect, la syntaxe est `std::array<int, 5>{1, 2, 3}`

`std::array` est un conteneur fixe avec initialisation par défaut.
</quiz>

<quiz>
Quelle est la complexité temporelle de `std::vector::push_back` ?
- [x] O(1) en moyenne
- [ ] Toujours O(n)
- [ ] O(log n)

En moyenne, `push_back` est constant, mais peut déclencher un reallocation (rare).
</quiz>

<quiz>
Pourquoi utiliser `std::move` ?
```cpp
std::string s1 = "Hello";
std::string s2 = std::move(s1);
```
- [x] Évite une copie coûteuse
- [ ] Permet de dupliquer un objet
- [ ] N'est utile que pour les pointeurs

`std::move` convertit un objet en rvalue, permettant des transferts efficaces.
Dans la question, on transfère la propriété de s1 vers s2.
</quiz>

<quiz>
Quelle est la différence entre `std::vector` et `std::deque` ?
- [x] `deque` permet des insertions/ suppressions rapides aux extrémités
- [ ] `vector` est toujours plus rapide
- [ ] Ils sont identiques en C++ moderne

`deque` (double-ended queue) est optimisé pour les opérations aux deux extrémités.
</quiz>

<quiz>
Comment implémenter un tableau 2D dynamique sans fuites ?
```cpp
std::vector<std::vector<int>> matrix(10, std::vector<int>(5));
```
- [x] Correct
- [ ] Il faut utiliser `new int*[10]` et `delete[]`
- [ ] Impossible sans `unique_ptr`

`std::vector` gère automatiquement la mémoire pour les tableaux 2D.
</quiz>

<quiz>
Quelle est la sortie de ce code ?
```cpp
int main() {
    auto ptr = std::make_unique<int>(42);
    int* raw = ptr.get();
    *raw = 10;
    std::cout << *ptr; // Affiche quoi ?
}
```
- [x] `10`
- [ ] `42`
- [ ] Erreur de compilation

`get()` ne change pas l'ownership, donc on peut modifier la valeur via le pointeur brut.
</quiz>

<!-- mkdocs-quiz results -->