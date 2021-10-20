# Description

Langage compilé orienté objet, le C++ permet d'alouer soi même ces unités mémoire. Comme le C son ancètre il est surtout utilisé pour faire du code embarqué ou lors de projets necessitant un maîtrise totale de la mémoire de son hardware.

## Concepts généraux :

- allocation d'espaces mémoire via les pointeurs
- fonctions
  - arguments optionnels
  - surcharge de méthodes
  - passage d'arguments par référence (modification de la var au sein de la fonction sans soucis de portée)
  - Argument de fonction optionnels : les arguments les plus à droite d'une fonction peuvent être rendu optionnels en leur donnant un valeur par défaut, exemple:
```cpp
//declaration
addition(int a = 0, int b =0, int c = 0){
    return a + b + c;
}
//utilistation
addition(4, 2) //=6
addition(); //=0
addition(4, 2, 4); //=10
addition(,12,2); //!\ crash car argument à gauche vide.
``` 
- une classe necessite 2 fichier
  - .cpp : contient le code exécuté, la partie fonctionnelle du code
  - .h : contient la définition de la classe auquel il est rattaché (eq. interface)
- pointeurs
  - en C++ on peut utiliser directement les pointeurs pour travailler uniquement par référence
  - déclaration : \*myVar
    faire référence à l'adresse d'une variable : &myVar

- Surcharge opérateur
```cpp
//dans le .h d'une classe en dehors de la classe
//opérateur <
bool operator==(MaClasse const& a, Maclasse const& b);
//dDéfinition de la fonction dans le cpp
bool operator==(MaClasse const& a, Maclasse const& b) {
    //Teste si a.m_heure == b.m_heure etc.  
    if (a.num1 == b.num1 && a.num2 == b.num2)
        return true;
    else
        return false;
}
```

- Méthodes vituellles : pmermettent la redefinition des dites méthodes dans les classes filles
- Classes vituelles, permettent lorsque qu'une classe hérite de deux classes, héritant de la même classe, d'instancier deux fois la classse la classe commune.
```cpp
class A {};
class B : public A {};
class C : public A {};
class D : public B, public C {};

//Instances mémoire pour D
A A
| |
B C
\ /
 D


class A {};
class B : public virtual A {};
class C : public virtual A {};
class D : public B, public C {};

//Instances mémoire pour D
 A
/ \
B C
\ /
 D
```