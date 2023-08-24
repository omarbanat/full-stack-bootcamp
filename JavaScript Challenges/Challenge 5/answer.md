```js 
const headerElement = document.querySelector("header");
const footerElement = document.querySelector("footer");
const menuDiv = document.querySelector(".menu");

console.log("header child is ", headerElement.childNodes);
console.log("footer child is ", footerElement.childNodes);
console.log("menuDiv child is ", menuDiv.childNodes);

const containerDiv = document.createElement("div");
containerDiv.className = "container";

const para = document.createElement("p");
para.textContent = "hello world";

containerDiv.appendChild(para);

document.body.appendChild(containerDiv);

containerDiv.style.backgroundColor = "blue";
para.style.color = "white";
para.style.fontSize = "24px";
para.style.fontFamily = "Helvetica";
para.style.border = "10px solid black";

const headings = document.querySelectorAll("h1, h2, h3, h4, h5, h6");
console.log(headings);
for (let heading of headings) {
  heading.style.fontStyle = "italic";
}

const heading3 = document.querySelector("h3");
heading3.style.fontStyle = "none";

const daniel = document.createElement("button");
daniel.textContent = "this is daniel";
document.body.appendChild(daniel);

daniel.addEventListener("mouseover", function () {
  this.style.background = "green";
});
daniel.addEventListener("mouseout", function () {
  this.style.background = "";
});

function eventL(type, color) {
  daniel.addEventListener(type, function () {
    this.style.background = color;
  });
}

eventL("mouseover", "green");
eventL("mouseout", "");

const buttonContainer = document.getElementById("buttonContainer");

buttonContainer.addEventListener("click", function (event) {
  console.log(event);
  // to target only the button
  if (event.target.tagName === "BUTTON") {
    // get the text of the button only
    console.log(event.target.textContent);
  }
});

const newForm = document.createElement("form");
let nameInput = document.createElement("input");
let emailInput = document.createElement("input");
let submitInput = document.createElement("button");

nameInput.type = "text";
emailInput.type = "text";
submitInput.type = "submit";

submitInput.textContent = "submit";
newForm.appendChild(nameInput);
newForm.appendChild(emailInput);
newForm.appendChild(submitInput);

// newForm.append(nameInput, emailInput, submitInput)

document.body.appendChild(newForm);

newForm.addEventListener("submit", function (event) {
  event.preventDefault();
  console.log(event.target[0].value);
  console.log(nameInput.value);
  // console.log(emailInput.value);
});

// clone la div
// 1. to get the div i want to clone
// 2. clone that div
// 3. append it to the body
// 4. change the p to cloned

const originalDiv = document.getElementById("original");
const clonedDiv = originalDiv.cloneNode(true);
clonedDiv.querySelector("p").textContent = "Cloned";

document.body.appendChild(clonedDiv);

const cloneButton = document.getElementById("clone-btn");
cloneButton.addEventListener("click", function () {
  // visible , hidden
  if (clonedDiv.style.display === "none") {
    clonedDiv.style.display = "block";
  } else {
    clonedDiv.style.display = "none";
  }
});


const removerHeaderButton = document.createElement('button')

removerHeaderButton.textContent = 'remove header'

removerHeaderButton.addEventListener('click', function(){
    headerElement.remove()
})

document.body.appendChild(removerHeaderButton)

function insertBeforeFooter(newElement){
    document.body.insertBefore(newElement, footerElement)
}

const newDiv = document.createElement('div')
newDiv.textContent = 'hayda new div'

insertBeforeFooter(newDiv)
```
