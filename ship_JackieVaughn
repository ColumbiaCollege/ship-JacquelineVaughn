//Star setup, mostly borrowed from Luna
class Star{
  float xpos=0;
  float ypos=100;
  float speed=5;
  PImage img;
  Star(){
    xpos=random(width);
    ypos=random(height);
    speed=10;
}
//star movement
void move(){
  xpos=xpos+speed;
  if(xpos>width){
    xpos=0;
    ypos=random(height);;
}
}
//star shape itself
void display(){
  fill(#ffffff);
  noStroke();
  ellipse(xpos,ypos,5,5);
}}
//declaring variables
float x=100;
float y=100;
float angle1=0.0;
float segLength=50;
PImage ship;
PImage BG;
//intializes stars
Star[]stars=new Star[100];
//window settings
void setup(){
  ship=loadImage("ship8.png");
  BG=loadImage("BG.png");
  size(1200,700);
  //star loop int
  for(int i=0;i<stars.length;i++){
    stars[i]=new Star();}
  }
void draw(){
  //background(#000066);
  image(BG,0,0,1200,700);
  //star loop act
  for(int i=0;i<stars.length;i++){
    stars[i].display();
    stars[i].move();
  }
  //ship being drawn (99% stolen from Processing example)
  float dx=mouseX-x;
  float dy=mouseY-y;
  angle1=atan2(dy,dx);
  x=mouseX-(cos(angle1)*segLength);
  y=mouseY-(sin(angle1)*segLength);
  segment(x,y,angle1);
  image(ship,x,y,200,200);
}
//also stolen from Processing example; makes the ship move with the mouse correctly
void segment(float x,float y,float a){
  pushMatrix();
  translate(x,y);
  rotate(a);
  line(0,0,segLength,0);
  popMatrix();
}
