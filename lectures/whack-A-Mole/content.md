# Whack-A-Mole

## Getting Started

###### Creating your html file and give it the basic template
You can begin by going to the code pen link that has the editor you will begin to work on


* [First Mole!]()

```html 
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Whack A Mole!</title>
  <link href='https://fonts.googleapis.com/css?family=Amatic+SC:400,700' rel='stylesheet' type='text/css'>
  <link rel="stylesheet" href="style.css">
</head>
<body>
</body>
</html>

```

## Making a Mole

##### Making one hole & Mole
To begin you're going to make a Mole in the body

```html
		<div class="game"> 
			<div class="hole hole1">
      		<div class="mole"></div>
    		</div>
		</div>
```


##### Adding your starter css

Next you are going to want to add your css for your game page

```css
html {
  box-sizing: border-box;
  font-size: 10px;
  background: #ffc600;
}
*, *:before, *:after {
  box-sizing: inherit;
}
body {
  padding: 0;
  margin: 0;
  font-family: 'Amatic SC', cursive;
}
h1 {
  text-align: center;
  font-size: 10rem;
  line-height: 1;
  margin-bottom: 0;
}
```

##### Making your mole go up and down

Under your game div tag your going to want to start with your `<script>` tag(Remeber `<script>` Tags is how we initiate javascript in our document.

```javascript 
<script>
  const holes = document.querySelectorAll('.hole');
  const scoreBoard = document.querySelector('.score');
  const moles = document.querySelectorAll('.mole');
  let lastHole;
  let timeUp = false;
  let score = 0;
</script>
```

* Here we are just adding our variables for what we will need


##### Making your Mole Pop up(peep)

You can start by adding a this javascript code under your variables.

```javascript
function peep() {
    const time = randomTime(200, 1000);// Where we set how long we want the mole to stay up
    const hole = randomHole(holes); // How we randomly choose which hole for the mole to pop up
    hole.classList.add('up');
    setTimeout(() => {
      hole.classList.remove('up');
      if (!timeUp) peep();
    }, time);
  }
```

***You'll notice `hole.classList.add('up');` is similar to our beatmaker project if you participated in that we added a class using javascript to change how the element looked***

Now of course your function isnt going to work until you finish the other functions that you called.

```javascript
 function randomTime(min, max) {
    return Math.round(Math.random() * (max - min) + min);
  }

  function randomHole(holes) {
    const idx = Math.floor(Math.random() * holes.length);
    const hole = holes[idx];
    if (hole === lastHole) {
      console.log('Ah nah thats the same one bud');
      return randomHole(holes);
    }
    lastHole = hole;
    return hole;
  }
```

Next we have to add the functionality of hitting our mole

```javascript
 function bonk(e) {
    if(!e.isTrusted) return; // cheater!
    score++;
    this.parentNode.classList.remove('up');
    scoreBoard.textContent = score;
  }
```

And then Starting our game 

```javascript
function startGame() {
    scoreBoard.textContent = 0;
    timeUp = false;
    score = 0;
    peep();
    setTimeout(() => timeUp = true, 10000)
  }
```

but wait how will we know when the mole is clicked if we dont add our listener?

``` javascript
 moles.forEach(mole => mole.addEventListener('click', bonk));
```
