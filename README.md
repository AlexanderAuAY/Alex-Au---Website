## Welcome to my website!

### Khan Academy - Fish Tank

```
background(89, 216, 255);
var centerX = 200;
var centerY = 100;
var bodyLength = 118;
var bodyHeight = 74;
var bodyColor = color(162, 0, 255);


var drawFish = function(centerX,centerY,bodyHeight,bodyColor)
{
noStroke();
fill(bodyColor);
// body
ellipse(centerX, centerY, bodyLength, bodyHeight);
// tail
var tailWidth = bodyLength/4;
var tailHeight = bodyHeight/2;
triangle(centerX-bodyLength/2, centerY,
         centerX-bodyLength/2-tailWidth, centerY-tailHeight,
         centerX-bodyLength/2-tailWidth, centerY+tailHeight);
// eye
fill(33, 33, 33);
ellipse(centerX+bodyLength/4, centerY, bodyHeight/5, bodyHeight/5);
} ;

drawFish (316,298,84,156);
drawFish (209,186,15,200);
drawFish (133,85,126,99);
```


### Khan Academy - JQuery Quiz

```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Challenge: jQuery trivia quiz</title>
<style>
#result {
background: rgb(255, 246, 204);
border: 2px dotted gold;
font-size: 24px;
height: 60px;
margin-top: 10px;
}
</style>
</head>
<body>

<h1>jQuery Quiz</h1>

<form id="trivia-form">
<label>
Who invented jQuery?<br>
<select id="trivia-answer">
<option value="eich">Brendan Eich</option>
<option value="resig">John Resig</option>
<option value="rossum">Guido van Rossum</option>
<option value="berners">Tim Berners-Lee</option>
</select>
</label> <br>
<button type="submit">Check Answer</button>
</form>
<div id="result"></div>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
<script>
$("#trivia-form").on("submit",function(event){
event.preventDefault();
var $answer = $("#trivia-answer");
var answer = $answer.val();
if(answer === "resig"){
$("#result").text("You are correct!")}
else {
$("#result").text("Try again!");
}

});
</script>
```
### Khan Academy - Mad Libs

```
<!DOCTYPE html>
<html>
 <head>
  <meta charset="utf-8" />
  <title>Challenge: Mad Libs</title>
 </head>
 <body>
 
    <h1>Mad Libs</h1>
     
    <ul>
      <li>Noun: <input type="text" id="noun"></li>
      <li>Adjective: <input type="text" id="adjective"></li>
      <li>Someone's Name: <input type="text" id="person"></li>
    </ul>
     
    <button id="lib-button">Lib it!</button>
      
    <p>Generated story: 
    <span id="story"></span>
    </p>
 
    <script>
        var libButton = document.getElementById('lib-button');
        var libIt = function() {
            var storyDiv = document.getElementById("story");
            storyDiv.innerHTML = "??Your story here";
            var noun = document.getElementById("noun").value;
            var adjective = document.getElementById("adjective").value;
            var person = document.getElementById("person").value;
            storyDiv.innerHTML = noun+" noun "+adjective+" adjective "+ person;
        };
        libButton.addEventListener('click', libIt);
        
    </script>
  
 </body>
</html>
```

### Khan Academy - Paint Splatter

```
var generator = new Random(1);
var standardDeviation = 6;
var mean = 0; 
  
    var paint = function() {
            this.x = 200;
            this.y = 200;
    };
   
    paint.prototype.display = function() {
        var length = random(20);
        noStroke();
        var first = generator.nextGaussian()*15;
        var rslot = standardDeviation * first + mean;
         var gslot = standardDeviation * first + mean-200;
          var bslot = standardDeviation * first + mean-100;
        fill(rslot, gslot, bslot);
        ellipse(this.x, this.y, length, length);
    };

paint.prototype.splatter = function() {
    var numx = generator.nextGaussian();
    var numy = generator.nextGaussian();
    var xmove = standardDeviation * numx + mean;
    var ymove = standardDeviation * numy + mean;
    
    this.x += xmove;
    this.y += ymove;
    
};


var p = new paint();

draw = function() {
    p.splatter();
    p.display();
};
```

### Khan Academy - Word Game

```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Project: Word game </title>
        <style>
            body { font-family: Arial, sans-serif;}
            form { font-size: 1.5em;}
            
            .scrambled, input, button {
                font-family: monospace;
                font-size: 2em;
            }
            
            .correct{
                display: none;
                position: absolute;
                top: 220px;
                left: 0px;
                background-color: yellow;
                font-weight: bold;
                border: solid 5px green;
                border-radius: 25px;
                height: 50px;
                width: 150px;
                text-align: center;
            }
            
            .incorrect{
                 display: none;
                position: absolute;
                top: 220px;
                left: 0px;
                background-color: pink;
                font-weight: bold;
                border: solid 5px red;
                border-radius: 25px;
                height: 50px;
                width: 150px;
                text-align: center;
            }
            
        </style>
    </head>
    <body>
    
    <h1>Word game!</h1>
    
    <div class="correct"><p>Correct, good job<p></div>
    <div class="incorrect"><p>Incorrect, try again<p></div>
    
    <form id="joke-form">
        <label>
            Unscramble these letters to form a word:<br>
            <span class="scrambled"></span><br>
            <input type="text" size="10">
        </label>
        <button type="submit">Check</button>
    </form>

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
    <script>
        var scrambled = ["rabdo","fnrieg","tianno","ocnea","eckch","mrasony","saec"];
        var answers = ["board","finger","nation","ocean","check","masonry","case"];

        var random = Math.floor((Math.random() * 7));
        $(".scrambled").text(scrambled[random]);
        $("#joke-form").on("submit", function(event){
            event.preventDefault();
            var $answer = $(this).find('[type=text]'); 
```
