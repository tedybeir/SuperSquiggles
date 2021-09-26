# SuperSquiggles
The repository of the SuperSquiggle Project for [cennznet grant](https://gitcoin.co/issue/cennznet/grants/9/100026471)  
You can generate your SuperSquiggle [here](https://preview.p5js.org/tedybeir/present/TZF8xmTcw)

# Technical Overview

But how the SuperSquiggle are generated ?  
For this we use the [P5js](https://p5js.org/) library  
P5js is processing library for javascript who permit to create shape and more with javascript code  

Each squiggle is in fact a following of many circle who have different colors , high and interval  
The generation of one squiggle is made by a function who take 3 arguments :   

1. __colorseed__ for generate different color
2. __yseed__ for generate different curve
3. __interval__ for generate different interval between the circle

The color seed is put in a noise function  
But why use a noise function instead of a random ?  
A Random function sort a number in an interval but a noise function sort a number between 0 and 1 who is "stable"  
The problem with the random function is it's too imprevisible  

Noise function to color and ball movement (random but previsible) :   
![noisegif](https://github.com/tedybeir/SuperSquiggles/blob/main/noisegif.gif)  

Random function to color and ball movement (entierly random , imprevisible and ugly) :  
![randomgif](https://github.com/tedybeir/SuperSquiggles/blob/main/randomgif.gif)  

But you have 1% of luck to have a squiggle with entirely random color  

The yseed is put also in a noise function for randomize the behavior of the y axis (if the curve go down or up)  

The interval is used to increment x each loop (the function is call inside a draw() so its loop indefinetly)  
It create squiggle with different ecart between each new circle  
More the interval is high more the curve will be clean and generated fast  

The draw function loop indefinetly so for stop the curve we put a little condition :  

```javascript
 if (x > width/10*9) {
    noLoop()
  } else {
    x += interval;
  } 
```
The SuperSquiggle have also special traits :  

* __numbersquigprob__ The probability of squiggle generated / 70% for 1 , 20% for 2 and only 10% for 3   
<img src="https://github.com/tedybeir/SuperSquiggles/blob/main/several.png" alt="stroke" width="500"/>  

* __colorflashprob__ The probability of squiggle using random function instead of noise / 10%  
<img src="https://github.com/tedybeir/SuperSquiggles/blob/main/flash.png" alt="stroke" width="500"/>  

* __strokeprob__ The probability of black stroke / 5%  
<img src="https://github.com/tedybeir/SuperSquiggles/blob/main/stroke.png" alt="stroke" width="500"/>

