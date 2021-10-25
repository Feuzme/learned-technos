# Description 
React est un framework de developpement FRONT Web, il repose sur le langage JAVASCRIPT et permet de concevoir des applications WEB avec une expérience utilisateur proche d'une application mobile.

## Concepts généraux : 
- Application web : 
	- tout se charge dès le lancement de l'app
	- Les changement déclenchent le rechargement des composants modifiés
	- même type d'UX qu'une application mobile
- Langage JavaScript : REACT utilise le JavaScript moderne et tout ces concepts
- State : permet de modifier dynamiquement les données d'un composant. /!\ Ne jamais modifier le state directement. exemple
	```js
	const [toggle, setToggle] = useState([1, 2, 3]);

	const toggleFunc = () => {
		const newArr = [...toggle]; //onrecopie les valeurs
		newArr.push(4); //on ajoute

		setToggle(newArr);//ensuite on set toggle avec les nouvelles valeurs  
	}
	```
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
	return args; //tableau des paramètres passés à la fonction
}
	```
- Hooks
	- toujours dans un composant react 
	- toujours à la racine de ce composant
- useEffect(() => {}, []) : execute la methode passée en paramètre, à la modification du paramètre passé dans le tableau, sans tableau s'exécute à chaque modification du state du composant. Si un state est passé en argument sera exécuté à la modification du state de ce composant (si tableau vide uniquement au chargement du composant)
- setInterval(()=>{}, interval) : permet de mettre en place un timer
- Event listener
	- addEventListener('event', function) : permet d'écouter des évennement hors du contexte de l'app window par exemple. Passer en argument l'event et la fonction a exécuter
	- removeEventListener('event', function) : stopper l'écoute de l'event passer en argument l'event et la fonction associée

	```js
	useEffect(() => {
    window.addEventListener('resize',actionResize);

    function actionResize(params) {
      console.log("RESIZED !");
    }

    return () =>{
      window.removeEventListener('resize', actionResize)
    }
  }, [])
	```
- props.children : retourne tout les éléments enfants d'un composant
	```html
	<Content> <!--enfants composant Content.js ici : h1 & p-->
        <h1>Article 1</h1>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Debitis commodi a, ipsum quod ut earum nostrum. Maiores aspernatur saepe dicta laudantium sint, repudiandae nam placeat, facere molestias, ratione doloremque dolore?</p>
    </Content>
	```
- React.memo(Composant) : ne se met à jour que lors de la modification des props du composant (pour les types primitifs)
	```js
	import React from 'react'

	function Content(props) {
		console.log("mise à jour");

		return (
			<div className="content">
				<h1>{props.num}</h1>
			</div>
		)
	}

	export default React.memo(Content);
	``` 
- useMemo(()=>{}, []) : permet de passer une valeur de référence à un composant enfin et ne le recharger que si le contenu change.
	```js
	function App() {
		const tableau = useMemo(()=> {
			return [1,2,3,4];
		}, [])
		
		return (
			<div className="App">
				<Content num ={tableau}/> //le composant ne rechargera que si les données du tableau sont mise à jour
				<button onClick={toggleFunc}>Toggle</button>
			</div>
		);
	}
	```
- useCallBack(()=>{}, []) : permet de passer une fonction à un composant et de ne le recharger qu'à un changement du paramètre entre crochet

## TODO : finir de resumer les concepts généraux