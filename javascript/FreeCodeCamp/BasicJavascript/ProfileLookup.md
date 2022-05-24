# problem info

Profile Lookup
We have an array of objects representing different people in our contacts lists.

A lookUpProfile function that takes name and a property (prop) as arguments has been pre-written for you.

The function should check if name is an actual contact's firstName and the given property (prop) is a property of that contact.

If both are true, then return the "value" of that property.

If name does not correspond to any contacts then return the string No such contact.

If prop does not correspond to any valid properties of a contact found to match name then return the string No such property.

``` javascript


// Setup
const contacts = [
  {
    firstName: "Akira",
    lastName: "Laine",
    number: "0543236543",
    likes: ["Pizza", "Coding", "Brownie Points"],
  },
  {
    firstName: "Harry",
    lastName: "Potter",
    number: "0994372684",
    likes: ["Hogwarts", "Magic", "Hagrid"],
  },
  {
    firstName: "Sherlock",
    lastName: "Holmes",
    number: "0487345643",
    likes: ["Intriguing Cases", "Violin"],
  },
  {
    firstName: "Kristian",
    lastName: "Vos",
    number: "unknown",
    likes: ["JavaScript", "Gaming", "Foxes"],
  },
];

function lookUpProfile(firstName, prop){
// Only change code below this line

// Only change code above this line
}

// Change these values to test your function
lookUpProfile("Akira", "likes");

```


# My Answer

``` javascript

// Setup
const contacts = [
  {
    firstName: "Akira",
    lastName: "Laine",
    number: "0543236543",
    likes: ["Pizza", "Coding", "Brownie Points"],
  },
  {
    firstName: "Harry",
    lastName: "Potter",
    number: "0994372684",
    likes: ["Hogwarts", "Magic", "Hagrid"],
  },
  {
    firstName: "Sherlock",
    lastName: "Holmes",
    number: "0487345643",
    likes: ["Intriguing Cases", "Violin"],
  },
  {
    firstName: "Kristian",
    lastName: "Vos",
    number: "unknown",
    likes: ["JavaScript", "Gaming", "Foxes"],
  },
];

function lookUpProfile(name, prop) {
  // Only change code below this line
  let nameInContact = false;
  for(let i = 0; i < contacts.length; i++){
    if(contacts[i].firstName == name){
      nameInContact = true;
    }

    if(contacts[i].firstName == name && contacts[i].hasOwnProperty(prop)){
      nameInContact = i;
      return contacts[i][prop];
    }
  }
  if(nameInContact == false){
    return "No such contact";
  }
  return "No such property";
  }

  // Change these values to test your function
  lookUpProfile("Akira", "likes");
  ```
 
  # Thought Process 
  Contacts is an Array so to access the objects in it, you can use a loop.
  The loop returns the value of the given prop if the name and prop are valid.
  For the other cases, I made a bool variable named nameInContact to check if the name was one of the values of the property firstName. If it wasn't, I would return the string "No such Contact". And if it made it to the end without returning at this point, then the only option would be to return "No such property".
    

    