# finalCP6
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Module5</title>
</head>
<body>
<h2>JavaScript to Create Objects</h2>

<p>Here object literal property will be shown here: <br><br><span id="demo1"></span></p>
<p>Here myGreeting() method will show result: <br><br><span id="demo2"></span></p>
<p>Here getProperties() method for object1 will show result: <span id="demo3"></span></p>
<p>Here getProperties() method for object2 will show result: <span id="demo4"></span>

<script>

// object literal
const myDog = {
name: "Bluey",
breed: "Australian Cattle Dog",
tvProgram: "Bluey",
notes: "A female anthropomorphic 6-year-old blue heeler puppy. She is curious and energetic."
};

// displaying object's property
document.getElementById("demo1").innerHTML = "Name: " + myDog.name + "<br>Breed: " + myDog.breed + "<br>TV Program Starred: " + myDog.tvProgram + "<br>Note: " + myDog.notes;

// adding a property to an Object literal
myDog.mySound = "Turning Adventures into Fun";

// an object constructor with funtion name myDogConst
function myDogConst(name, breed, tvProgram, notes, mySound, canTalk){
this.name = name;
this.breed = breed;
this.tvProgram = tvProgram;
this.notes = notes;
this.mySound = mySound;
this.canTalk = canTalk;
}

// an object created using object constructor
const myDog2 = new myDogConst("Bluey", "Australian Cattle Dog","Bluey",
"A female anthropomorphic 6-year-old blue heeler puppy. She is curious and energetic.","Turning Adventures into Fun", true);


 // two new objects
 const myDog3 = new myDogConst("Krypto", "Kryptonian","Superman",

"Super Dog; An alien's best friend.","I'm powered by the yellow Sun", true);

 const myDog4 = new myDogConst("Scooby Doo", "Great Dane","Scooby-Doo, Where Are You!",

 "The dog that solves mysteries.","Scoobie Doobie Dooooooo!", true);

// function to view properties
myDog3.getProperties = function(){
   let x;
   // for loop to view myDog3 properties
   for (const prop in myDog3) {
      if (Object.hasOwn(myDog3, prop) && prop!= "getProperties") {
        x += `<br>The dog's ${prop} is ${myDog3[prop]}`;
      }
   }
   return x;


}

// function to view properties
myDog4.getProperties = function(){
   let x;
    // for loop to view myDog4 properties
   for (const prop in myDog4) {
      if (Object.hasOwn(myDog4, prop) && prop!= "getProperties") {
        x+=`<br>The dog's ${prop} is ${myDog4[prop]}`;
      }
   }
   return x;

}

// myGreeting() method

myDog2.myGreeting = function(value){
		let text = "";
		if(value === undefined){
        	return "I can talk!";
        }
        else{
        	text = text.concat(value);;

            if (this.canTalk === true){
            text = text.concat(" Hello my name is " + this.name + ", "+ this.mySound +". I starred in the tv show " + this.tvProgram + ". My Character was a " + this.breed + ". I was " + this.notes);
            }
            else {
                text = text.concat(" "+this.name + " can not talk, "+ this.mySound + ". It starred in the tv show " +
    this.tvProgram + ". Its character was a "+this.breed + ". It was "+this.notes);
            }
        }

        return text;

 }



// calling myGreeting method of the object:

document.getElementById("demo2").innerHTML = myDog2.myGreeting("Roof!!");

document.getElementById("demo3").innerHTML = myDog3.getProperties();

document.getElementById("demo4").innerHTML = myDog4.getProperties();

</script>
</body>
</html>
