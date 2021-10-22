# Description 
React est un framework de developpement FRONT Web, il repose sur le langage JAVASCRIPT et permet de concevoir des applications WEB avec une expérience utilisateur proche d'une application mobile.

## Concepts généraux : 
- Application web : 
	- tout se charge dès le lancement de l'app
	- Les changement déclenchent le rechargement des composants modifiés
	- même type d'UX qu'une application mobile
- Langage JavaScript : REACT utilise le JavaScript moderne et tout ces concepts
- State : permet de modifier dynamiquement les données d'un composant
- Les props servent a transférer des données entre composants
- spread operator : ...
```js
//example
const a = [1,2,3];
console.log(a); //[1,2,3]
const b = [...a, 4];
console.log(b); // [1,2,3,4]
```
- rest operator : ...
```js
//example
function func(...args){ //premet à la fonction de rendre plusieur arguments sous forme d'un tableau
	return args;
}
```

# TODO : finir de resumer les concepts généraux