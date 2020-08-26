# PianoKeys
Helping beginner-level piano students study
Using JavaScript, CSS and HTML, I created an interactive game to help out piano students who starting to learn how play to understand the piano keyboard using simple phrases to play. For this project I have them play the first two lines of "Happy Birthday".
Under JS, I start out creating variables for a 'keys' and 'notes' array. With the 'notes' function, I use a loop to go through the elements of the keys array and pushing them to the notes array.:

const keys = ['c-key', 'd-key', 'e-key', 'f-key', 'g-key', 'a-key', 'b-key', 'high-c-key', 'c-sharp-key', 'd-sharp-key', 'f-sharp-key', 'g-sharp-key', 'a-sharp-key'];
const notes =[];
keys.forEach(function(key){
  notes.push(document.getElementById(key));
})

I then create a function called 'keyPlay' that changes the background color when the keys are pressed down.  In this case the color will be 'green':

const keyPlay = function(event){
  event.target.style.backgroundColor = "green";
}

Right after I create a function called 'keyReturn' where it returns the background color to its default.  For this, I inputted an empty string:

const keyReturn = function(event){
event.target.style.backgroundColor = '';
}

After creating those functions, I assigned them as values to event handler properties:

let handler = function(note){
  note.onmousedown = function(){
    keyPlay(event);
  }
  note.onmouseup = function(){
    keyReturn(event);
  }
}

Create a loop that runs the array through the function:

notes.forEach(handler);

Next, created variables that store buttons that progress the user through the lyrics:

let nextOne = document.getElementById('first-next-line');
let nextTwo = document.getElementById('second-next-line');
let nextThree = document.getElementById('third-next-line');
let startOver = document.getElementById('fourth-next-line');

Since we are doing the beginning of the song, the only button the students need is 'nextOne' so I create 'hidden' properties for the rest of the variables to mark them as true:

nextTwo.hidden = true;
nextThree.hidden = true;
startOver.hidden= true;


