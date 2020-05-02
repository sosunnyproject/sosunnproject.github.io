---
layout: post
categories: creativecoding
title: "Nature of Code - Vectors"
date: 2020-04-25T14:01:27-05:00
last_modified_at: 2020-04-25T14:01:27-05:00
share: false
---

## 1.1 Bouncing ball with no vectors

벡터 클래스 이용 없이 위치, 속력 이동 계산.

```js
let x = 100; 
let y = 100;
let xspeed = 1;
let yspeed = 3.3;

function setup(){
  createCanvas(300, 300);
  background(255);
}

function draw(){
  background(255);

  x += xspeed;
  y += yspeed;

  if((x > width) || (x < 0)){
    xspeed = xspeed * -1;
  } 
  if((y > height) || (y < 0)){
    yspeed = yspeed * -1;
  }

  stroke(0);
  fill(175);
  ellipse(x, y, 20, 20);
}
```

### physics variables
- location
- speed
- acceleration
- target location
- wind
- friction

## 1.2 Vectors for Processing Programmers
- new location = velocity applied to current location
- location, velocity
- [p5.Vector 클래스 활용](https://p5js.org/reference/#/p5.Vector)
  - components of vector: x, y, z
  - magnitude: mag()
  - direction: heading()
  - vector 계산용 math API 따로 있음. 단순 +, -, * 연산 불가

```js
let loc;
let vel;
let r = 20;

function setup(){
  createCanvas(300, 300);
  background(255);
  loc = createVector(100, 100);  
  vel= createVector(1, 3.3);
}

function draw(){
  background(255);

  loc = loc.add(vel);
  if((loc.x > width) || (loc.x < 0)){
    vel.x = vel.x * -1; // 벡터 연산이 아님
  }
  if((loc.y > height) || (loc.y < 0)){
    vel.y = vel.y * -1;
  }

  stroke(0);
  fill(175);
  ellipse(loc.x, loc.y, r, r);
}
```

## 1.3 Vector Addition 

- exercise 1.1: separate x, y variables --> use p5.Vector class
- exercise 1.2: walker example from introduction and convert it to use PVectors
  - [practice](https://editor.p5js.org/sosunnyproject/sketches/LdMuFLOKh)
- exercise 1.3: Extend bouncing ball with vectors example into 3D. Make sphere to bounce around a box 
  - [3d + lighting + bouncing ball](https://editor.p5js.org/sosunnyproject/sketches/xvXto_pKO)
  - [lighting 3d tutorial](https://www.notion.so/Light-in-P5-90f4a5b4d66b4a97ad0c71bea4c9f59b)
