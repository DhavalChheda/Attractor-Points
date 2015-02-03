# Attractor-Points
int actRandomSeed = 0;
int max_distance = 600; 
 
void setup(){
  size(600, 600, P3D);
}
 
void draw() {
 
  background(255);
  smooth();
  noFill();
 
  randomSeed(actRandomSeed);
 
  stroke(0,180);
  strokeWeight(3);
 
  for (int gridY=0; gridY<width; gridY+=25) {
    for (int gridX=0; gridX<height; gridX+=25) {
 
      float diameter = dist(mouseX, mouseY, gridX, gridY);
      diameter = diameter/max_distance * 40;
      pushMatrix();
      translate(gridX, gridY, diameter*5);
      
      ellipse(0, 0, diameter, diameter);    
      popMatrix();
    }
  }
 
}
