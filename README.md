boolean c=false;
boolean e=false;

void setup() {
  size(600, 600, P3D);
}

void draw() {
  background(0);
  fill(255);
  rect(20, 550, 60, 30);
  rect(90, 550, 60, 30);
  fill(0);
  textSize(12);
  text("Cubo (c)", 25, 570);
  text("Esfera (e)", 95, 570);
  if (e) {
    background(0);
    camera(250, 250, 250/tan(PI/6), mouseX, mouseY, 0, 0, -1, 1);
    translate(width/2, height/2, -100);
    ambientLight(100, 0, 90);
    fill(100, 10, 80);
    stroke(225);
    sphere(200);
  }
  if (c) {
    background(0);
    camera(250, 250, 250/tan(PI/6), mouseX, mouseY, 0, 0, -1, 1);
    translate(width/2, height/2, -100);
    noFill();
    stroke(225);
    box(200);
  }
}

void keyPressed() {
  if (key=='e' || key=='c') {
    if (key=='e') {
      e=true;
      c=false;
    }
    if (key=='c') {
      e=false;
      c=true;
    }
  } else {
    e=false;
    c=false;
  }
}
