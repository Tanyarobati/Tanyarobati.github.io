---
layout: posts
title: my fractalls
---
<img src="../assets/images/6.png">
<h5 style="text-align:center;">A fractal tree is a tree made up by creating recursive branching in a graphics module in python.
i used turtle module.
first of all ,i imported turtle module .
Then i needed branches which the basic idea of it is to go forward , then a little bit left ,then back to the origin and move right to make a ("Y") shape .
after all , repeating it on a loop with reducing distance and here we go !!!</h5>

<pre>
import turtle
turtle.speed(0)
def square():
    turtle.fillcolor("Wheat3")
    turtle.begin_fill()
    n=2
    for i in range(n):
        turtle.forward(300)
        turtle.right(90)   
        turtle.forward(20)
        turtle.right(90)
    turtle.end_fill() 
square()    
turtle.forward(150)
turtle.left(90)

def star(n,d,c):
    turtle.fillcolor(c)
    turtle.begin_fill()
    for i in range(n):
        turtle.right(180-180/n)
        turtle.forward(d)
    turtle.end_fill() 

def tree(d,r,s):
    turtle.pensize(s)
    if d<1 :
        return
    if d>=20:
        turtle.pencolor("chocolate4")
    if 5<d<20:
        turtle.pencolor("DarkOrange")  
    if d<=5:
        turtle.pencolor("Red")    
    turtle.forward(d)
    turtle.left(r)
    tree(0.7*d,r,s*0.7)
    turtle.right(2*r)
    tree(0.7*d,r,s*0.7)
    turtle.left(r)
    turtle.backward(d)
    
    if 9<d<20:
        turtle.pencolor("DarkOrange")
        star(7,25,"DarkOrange")
turtle.tracer(0)
tree(80,35,6)
turtle.update()
turtle.exitonclick()
</pre>
<hr>

<img src="../assets/images/Screenshot 2023-11-11 002324.png">
<h4 style="align-center:center;">Fractals are objects that tend to have self-similar structures repeated a finite number of times.
The objective of this article is to draw a star fractal where a star structure is drawn on each corner of the star
and this process is repeated until the input size reduces to a value of x.
I use turtle module to achieve that .
As you can see i have 2 different types of stars.
first one is a five-corner-star and second one is a nine-corner-star.
i used random module to give me random colors for coloring my stars!!</h4>

<pre>import turtle
import random


def frac_star(n,d):
    if d<5:
        return

    for _ in range(n):
        turtle.forward(d)
        frac_star(n,d*0.2,)
        turtle.right(180-180/n)
   
    turtle.update()
#turtle.speed(0)
turtle.tracer(0)
turtle.penup()    
turtle.setpos(-600,0)   
turtle.pendown() 
turtle.fillcolor(random.random(),random.random(),random.random())
turtle.begin_fill()
frac_star(5,150)
turtle.end_fill()
turtle.penup()
turtle.setpos(-100,0)   
turtle.pendown() 
turtle.fillcolor(random.random(),random.random(),random.random())
turtle.begin_fill() 
frac_star(9,200)
turtle.end_fill()
turtle.penup()
turtle.setpos(400,0)   
turtle.pendown()
turtle.fillcolor(random.random(),random.random(),random.random())
turtle.begin_fill()   
frac_star(5,150)
turtle.end_fill()

turtle.mainloop()        
</pre>
<hr>
<img src="../assets/images/Screenshot 2023-11-11 202713.png">
<h4 style="text-align:center;">Fractals are objects that tend to have self-similar structures repeated a finite number of times.
Sierpinski triangle is a fractal and attractive fixed set with the overall shape of an equilateral triangle.
It subdivides recursively into smaller triangles
I use turtle module to achieve that .
i still struggle to fill_color it So there is no advice for you ~~~</h4>
<pre>import turtle
import random
turtle.bgcolor("black")
# turtle.pencolor("white")

def fractal_tri(d):
    if d<10:
        return

    for i in ["red","red","blue"]:
        turtle.pencolor(i)
        fractal_tri(d/2)
        turtle.forward(d)
        turtle.left(120)
    turtle.update()
turtle.tracer(0)    

#turtle.speed(0)   
turtle.fillcolor("white")
turtle.begin_fill()     
fractal_tri(200)
turtle.end_fill()        

turtle.mainloop()</pre>
<hr>
<img src="../assets/images/Screenshot 2023-11-11 203027.png">
<h4 style="text-align:center;">Fractals are objects that tend to have self-similar structures repeated a finite number of times.
The objective of this article is to draw a square fractal until the input size reduces to a value of x.
for achieving this, i used turtle module .
tip: if you reduce size half the way it was before , you get a grade page which is not very interesting!!
instead , you can give it 0.3,0.7/0.4,0.6 numbers to make it more thrilling!!
and if you even want more , you can use random module to randomize its colors!</h4>
<pre>import turtle
import random
#turtle.bgcolor(random.random(),random.random(),random.random())
def square(a):
    if a < 10 :
        return
    turtle.fillcolor(random.random(),random.random(),random.random())
    turtle.begin_fill()
    for _ in range(4):
        square(a*0.4)
        turtle.forward(a*0.6)
        turtle.left(90)
    
    turtle.end_fill()    
    turtle.update()
#turtle.speed(0)
turtle.tracer(0)
square(400) 
turtle.mainloop()
</pre>
