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