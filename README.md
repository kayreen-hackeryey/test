<div class="container">
  <h1>test</h1>
  <div class="buttons">
    <button id="yesButton">Yes</button>
    <button id="noButton">No</button>
 





const noButton = document.getElementById('noButton');
const yesButton = document.getElementById('yesButton');
const bunny = document.getElementById('bunny');
const sprinklesContainer = document.getElementById('sprinkles');

noButton.addEventListener('click', () => {
  const x = Math.random() * (window.innerWidth - noButton.offsetWidth);
  const y = Math.random() * (window.innerHeight - noButton.offsetHeight);
  noButton.style.position = 'absolute';
  noButton.style.left = `${x}px`;
  noButton.style.top = `${y}px`;
});

yesButton.addEventListener('click', () => {
  bunny.style.display = 'block';
  noButton.style.display = 'none';
  yesButton.style.display = 'none';
  document.querySelector('h1').innerText = 'Yayyyy! You said YES! 🎉';

  // Start sprinkles animation
  createSprinkles();
});

function createSprinkles() {
  const sprinkleCount = 100; // Number of sprinkles
  for (let i = 0; i < sprinkleCount; i++) {
    const sprinkle = document.createElement('div');
    sprinkle.classList.add('sprinkle');
    sprinkle.style.left = `${Math.random() * 100}vw`;
    sprinkle.style.animationDuration = `${Math.random() * 2 + 1}s`;
    sprinkle.style.animationDelay = `${Math.random() * 2}s`;
    sprinkle.style.backgroundColor = `hsl(${Math.random() * 360}, 70%, 60%)`;
    sprinklesContainer.appendChild(sprinkle);
  }
