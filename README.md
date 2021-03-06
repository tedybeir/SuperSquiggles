# SuperSquiggles
Repository of the SuperSquiggle Project for [cennznet grant](https://gitcoin.co/issue/cennznet/grants/9/100026471)  
SuperSquiggle is an ANIMATED GenerativeArt project who have endless squiggle possibility  
🔥 <span style="color:red">You can generate your SuperSquiggle </span> ➡ [HERE](https://preview.p5js.org/tedybeir/present/TZF8xmTcw) ⬅  🔥  
__If you want to save your SuperSquiggle , just click on the canvas and it will save it__   
(*refresh the page for generate another*)  
![squigglegif](https://github.com/tedybeir/SuperSquiggles/blob/main/squigglediscover.gif) 

# Technical Overview

But how the SuperSquiggle are generated ?  
We use the [P5js](https://p5js.org/) library  
P5js is processing library for javascript who permit to create shape and more with javascript code  

Each squiggle is in fact just a following of many circle who have different colors , high and interval  

```javascript
 //create an ellipse who take x and y for location and a size of 100
 ellipse(x, y, 100, 100)
```  
You will see below how the coordinates are generated etc ...  
The generation of one squiggle is made by a function who take 3 arguments :   

1. __colorseed__ for generate different color
2. __yseed__ for generate different curve
3. __interval__ for generate different interval between the circle

___The color seed is put in a noise function__  
But why use a noise function instead of a random ?  
A Random function sort a number in an interval but a noise function sort a number between 0 and 1 who is "stable"  
The problem with the random function is it's too imprevisible  

Noise function to color and ball movement (random but previsible) :   
![noisegif](https://github.com/tedybeir/SuperSquiggles/blob/main/noisegif.gif)  

Random function to color and ball movement (entierly random , imprevisible and ugly) :  
![randomgif](https://github.com/tedybeir/SuperSquiggles/blob/main/randomgif.gif)  

(But you have 8% of luck to have a squiggle with entirely random color)  

__The yseed is put also in a noise function for randomize the behavior of the y axis (if the curve go down or up)__  

__The interval is used to increment x each loop (the function is call inside a draw() so its loop indefinetly)__    
It create squiggle with different ecart between each new circle  
More the interval is high more the curve will be clean and generated fast  

Curve with low interval :  
<img src="https://github.com/tedybeir/SuperSquiggles/blob/main/assets/lowinterval.png" alt="stroke" width="500"/>   

Curve with high interval :  
<img src="https://github.com/tedybeir/SuperSquiggles/blob/main/assets/highinterval.png" alt="stroke" width="500"/>  

The SuperSquiggle have also special traits who change all :  

* __numbersquigprob__ The probability of several squiggles generated / 70% for 1 , 20% for 2 and only 10% for 3   
<img src="https://github.com/tedybeir/SuperSquiggles/blob/main/assets/several.png" alt="stroke" width="500"/>  

* __colorflashprob__ The probability of squiggle using random function instead of noise (create flashy curve) / 8%  
<img src="https://github.com/tedybeir/SuperSquiggles/blob/main/assets/flash.png" alt="stroke" width="500"/>  

* __strokeprob__ The probability of black stroke / 10%  
<img src="https://github.com/tedybeir/SuperSquiggles/blob/main/assets/stroke.png" alt="stroke" width="500"/>

* __palettecolor__ The probability of the palette of color choose / 5% for the dark red palette , 80% for the basic palette , 10% for the cloud palette and 5% for the kaki palette  

The palette color is choose by the palettecolor variable , existing 4 differents colors palettes :  

1. The BASIC palette  
<img src="https://github.com/tedybeir/SuperSquiggles/blob/main/squiggle.png" alt="stroke" width="500"/>

2. The DARKRED palette  
<img src="https://github.com/tedybeir/SuperSquiggles/blob/main/assets/darkred.png" alt="stroke" width="500"/>

3. The CLOUD palette  
<img src="https://github.com/tedybeir/SuperSquiggles/blob/main/assets/cloudpalette.png" alt="stroke" width="500"/>

4. The Kaki palette  
<img src="https://github.com/tedybeir/SuperSquiggles/blob/main/assets/kakipalette.png" alt="stroke" width="500"/>  
   
All these variables are used to draw one circle and it's repeated cause the draw function loop indefinetly  
So for stop the curve we put a little condition who check if the curve isnt after the 9/10 of the screen :  

```javascript
 if (x > width/10*9) {
    noLoop() //stop the loop
  } else {
    x += interval; //moove the curve forward
  } 
```  

The size of the canvas can also be change like you want , i have put many example of size of canvas in this [folder](https://github.com/tedybeir/SuperSquiggles/edit/main/examples)  
(*Try to zoom and dezoom for find your favorite size (personnaly i love this canvas with zoom at 25%*)
<img src="https://github.com/tedybeir/SuperSquiggles/blob/main/examples/showfolder.png" alt="showfolder" width="450"/>   

# NFT Creation  

For the situation of mint like [ArtBlock](https://artblocks.io/) we can use hash of transaction and slice it for create deterministic output  
We can mint the SuperSquiggle like a gif or like a png  
Are both with hidden storage feature on [OpenSea](https://opensea.io/) (Sell image and only the owner can see the gif)  
You can contact me at __tedybeir@gmail.com__ if you have any questions or if you want to create an NFT with the SuperSquiggles  
Inspirated by the famous squiggle of artblock , but NOT a steal of code cause the artblock code isnt open :( and they are have many difference detailled above ⬆   
[HERE](https://github.com/tedybeir/SuperSquiggles/edit/main/examples) you can see some random SuperSquiggles i have generated for show you the diversity and the beauty    
But remember , for create your opinion you can generate your own SuperSquiggle [here](https://preview.p5js.org/tedybeir/present/TZF8xmTcw)  
or here => https://preview.p5js.org/tedybeir/present/TZF8xmTcw  
__If you want to save your SuperSquiggle , just click on the canvas and it will save it__  

![squigglegif](https://github.com/tedybeir/SuperSquiggles/blob/main/squiggle.gif) 
