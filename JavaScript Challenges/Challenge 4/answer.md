````javascript
let fiveNumbers = [1,2,3,4,5]

let personalInfo = {
    name : "Daniel", 
    age:  28, 
    height: "178CM", 
    location: "Beirut", 
    nationality: "Lebanese"
}

const additionalInfo = {
    occupation: "Trainer", 
    hobby: "Video Games", 
    education: "CCE"
}

const nextThreeNumbers = [6,7,8]

const allNumbers = [...fiveNumbers, ...nextThreeNumbers]

const fullInfo = {...personalInfo, ...additionalInfo}

const [, , ,fourth, fifth] = fiveNumbers

console.log(fourth, fifth)

const {name, location, nationality} = personalInfo

console.log(name, location, nationality)

personalInfo.contactInfo = {
    website: "danielawde9.com",
}

const {contactInfo: {email, website }} = personalInfo

console.log(email, website)

const [numb1, numb2, ...restNumbers] = fiveNumbers

console.log(restNumbers)

let toyota = {
    model: "2022",
    tires : 4
}

let kawazaki = {
    model: "2023",
    type: "Moto"
}


const vehicle = { ...toyota, ...kawazaki} 

console.log(vehicle)



```