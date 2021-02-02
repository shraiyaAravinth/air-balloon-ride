var balloon,balloonImg;
var backgroundImage;
var database,position;

function preload(){
  backgroundImage = loadImage("bg.png")
  balloonImg = loadAnimation("b1.png","b2.png","b3.png");
}
function setup() {
  createCanvas(900,500);
  balloon = createSprite(80,360,80,80);
  balloon.addAnimation( "moving",balloonImg);
  balloon.scale = 0.5;

  
}

function draw() {
  background(backgroundImage);  
  

  if(keyDown(LEFT_ARROW)){
    balloon.x = balloon.x -10;
}
else if(keyDown(RIGHT_ARROW)){
    balloon.x = balloon.x +10;
}
else if(keyDown(UP_ARROW)){
   balloon.y = balloon.y -10;
}
else if(keyDown(DOWN_ARROW)){
    balloon.y = balloon.y +10;
}
  drawSprites();
}
var balloonPosition=database.ref('balloon/height');
balloonPosition.on("value",readPosition,showError);

function updateHeight(x,y){
  database.ref('balloon/height').set({
    'x': height.x + x,
    'y': height.y + y
  })
}

function readHeight(data){
  height = data.val();
  balloon.x = height.x;
  balloon.y = height.y;
}

function showError(){
  console.log("Error in writing to the database")
}
