```js 

// DOM Tree Navigation
const menuDiv = document.querySelector('.menu');
const headerElement = document.querySelector('header');
const footerElement = document.querySelector('footer');

console.log('Child elements of menu div:', menuDiv.childNodes);
console.log('Child elements of header:', headerElement.childNodes);
console.log('Child elements of footer:', footerElement.childNodes);

// DOM Element Creation
const containerDiv = document.createElement('div');
containerDiv.className = 'container';

const paragraph = document.createElement('p');
paragraph.textContent = 'Hello, World!';
containerDiv.appendChild(paragraph);

document.body.appendChild(containerDiv);

// Element Styling
containerDiv.style.backgroundColor = 'blue';
paragraph.style.color = 'white';
paragraph.style.fontSize = '24px';
paragraph.style.fontFamily = 'Helvetica';
paragraph.style.border = '1px solid black';

const headings = document.querySelectorAll('h1, h2, h3, h4, h5, h6');
headings.forEach(heading => {
    heading.style.fontStyle = 'italic';
});

// Multiple Event Listeners
const hoverButton = document.createElement('button');
hoverButton.textContent = 'Hover Over Me';
document.body.appendChild(hoverButton);

hoverButton.addEventListener('mouseover', function() {
    this.style.backgroundColor = 'green';
});

hoverButton.addEventListener('mouseout', function() {
    this.style.backgroundColor = '';
});

// Event Delegation
const buttonContainer = document.getElementById('buttonContainer');
buttonContainer.addEventListener('click', function(e) {
    if (e.target.tagName === 'BUTTON') {
        console.log(e.target.textContent);
    }
});

// Form Data Extraction
const form = document.createElement('form');

const nameLabel = document.createElement('label');
nameLabel.textContent = 'Name: ';
const nameInput = document.createElement('input');
nameInput.type = 'text';
nameLabel.appendChild(nameInput);

const emailLabel = document.createElement('label');
emailLabel.textContent = 'Email: ';
const emailInput = document.createElement('input');
emailInput.type = 'email';
emailLabel.appendChild(emailInput);

const submitButton = document.createElement('button');
submitButton.textContent = 'Submit';

form.append(nameLabel, emailLabel, submitButton);
document.body.appendChild(form);

form.addEventListener('submit', function(e) {
    e.preventDefault();
    console.log('Name:', nameInput.value);
    console.log('Email:', emailInput.value);
});


// DOM Cloning
const originalDiv = document.getElementById('original');
const clonedDiv = originalDiv.cloneNode(true);
clonedDiv.querySelector('p').textContent = 'Cloned';
document.body.appendChild(clonedDiv);
clonedDiv.style.display = 'none';

const cloneButton = document.getElementById('clone-btn');
cloneButton.addEventListener('click', function() {
    if (clonedDiv.style.display === 'none') {
        clonedDiv.style.display = 'block';
    } else {
        clonedDiv.style.display = 'none';
    }
});

// Element Removal
const removeHeaderButton = document.createElement('button');
removeHeaderButton.textContent = 'Remove Header';
document.body.appendChild(removeHeaderButton);

removeHeaderButton.addEventListener('click', function() {
    headerElement.remove();
});

// Inserting Elements
function insertBeforeFooter(element) {
    footerElement.insertAdjacentElement('beforebegin', element);
}

const newDiv = document.createElement('div');
newDiv.textContent = 'New Div before Footer';
insertBeforeFooter(newDiv);

```
