# project related to Dom
## project link
[click me](https://stackblitz.com/edit/dom-project-chaiaurcode-qytxa9hf?file=index.html)

# Solution Code 
## project 1
```javascript
console.log("hitesh")
const buttons = document.querySelectorAll(".button");
console.log(buttons);
const body = document.querySelector("body")
buttons.forEach(function (button){
  console.log(button);
  button.addEventListener('click', function(e){
    console.log(e)
    console.log(e.target)
  if(e.target.id === 'grey'){
    body.style.backgroundColor = e.target.id
  }
  if(e.target.id === 'white'){
    body.style.backgroundColor = e.target.id
  }
 if(e.target.id === 'blue'){
    body.style.backgroundColor = e.target.id
  }
 if(e.target.id === 'yellow'){
    body.style.backgroundColor = e.target.id
  }
   if(e.target.id === 'purple'){
    body.style.backgroundColor = e.target.id
  }
  });
});

```
## Project 2 Solution
``` javascript
const form = document.querySelector('form');
console.log(form)
const height = document.querySelector('#height');
const weight = document.querySelector('#weight');
const results = document.querySelector('#results');
form.addEventListener('submit', function (e) {
  e.preventDefault();
const height = parseInt(document.querySelector('#height').value);
const weight = parseInt(document.querySelector('#weight').value);
const results = document.querySelector('#results');
if(height === '' || height < 0 || isNaN(height)){
results.innerHTML = `Please give a valid height ${height}`;
}
else if(weight === '' || weight < 0 || isNaN(weight)){
  results.innerHTML = `Please give a valid weight ${weight}`;
  }
  else {
const BMI = (weight/((height*height)/1000)).toFixed(2)
  // show the result 
  results.innerHTML = `<span> hi ${BMI}</span>`;
    if(BMI < 18.6){
      results.innerHTML = `<span> Under wight ${BMI}</span>`;
    }
    else
    if(18.6 < BMI < 24.9 ){
      results.innerHTML = `<span> Normal weight ${BMI}</span>`;
    }
    if(BMI > 24.9){
      results.innerHTML = `<span> Over wight ${BMI}</span>`;
    }
  }
})

```
## Project 3
```javascript
//both are same
const clock = document.getElementById('clock');
//const clock = document.querySelector('#clock');
setInterval(function(){
  let date = new Date()
  //console.log(date.toLocaleTimeString())
  clock.innerHTML = date.toLocaleTimeString();
},1000)//time at change in 1 second
```
## Project 4
```javascript
let randomNu = (parseInt(Math.random()*10+1));
const submit = document.querySelector('#subt');
const userInput = document.querySelector('#guessField');
const guessSlot = document.querySelector('.guesses');const remaining = document.querySelector('.lastResult');
const lowOrhigh = document.querySelector('.lowOrHi');
const startOver = document.querySelector('.resultParas');
const p = document.createElement('p');
let preguess = []
let Nuguess = 1
let playGame = true
if(playGame){
  submit.addEventListener('click', function(e){
    e.preventDefault();
    const guess = parseInt(userInput.value);
    console.log(guess);
   validateGuess(guess);
  });
}
function validateGuess(guess){
if(isNaN(guess)){
alert("please enter a valid value-");
}
else if(guess < 1){
  alert("please enter a number more than 1-");
}
else if(guess > 100){
  alert("please enter a number less than 100 ");
}
else{
  preguess.push(guess)
  if(Nuguess === 11){
    displayGuess(guess)
    displayMessage(`Game over, Random number was ${randomNu}`)
    endGame()
  }
  else{
    displayGuess(guess)
    checkGuess(guess)
  }
}
}
function checkGuess(guess){
if(guess === randomNu){
  displayMessage(`you guessted right`)
}else if(guess < randomNu){
displayMessage(`Number is tooo low`)
}
else if(guess > randomNu){
displayMessage(`Number is tooo high`)
}
}
function displayGuess(guess){
userInput.value = ''
guessSlot.innerHTML +=`${guess},   `
Nuguess++;
remaining.innerHTML = `${11-Nuguess} `
}

function displayMessage(message){
lowOrhigh.innerHTML = `<h2>${message}</h2>`
}
function NewGame(){
const newGameButton = document.querySelector('#newGame')
newGameButton.addEventListener('click', function(e){
  randomNu = (parseInt(Math.random()*10+1));
  preguess = []
  Nuguess = 1
  guessSlot = ''
  remaining.innerHTML = `${11-Nuguess}`;
  userInput.removeAttribute('disabled')
  startOver.removeChild(p)
    playGame = true;
});
}

function endGame(){
userInput.value = ''
userInput.setAttribute('disabled','')
p.classList.add('button')
p.innerHTML = `<h2 id="newgame"> start new game </h2>`
startOver.appendChild(p)
playGame = false
NewGame();
}
```