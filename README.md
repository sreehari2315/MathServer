# Ex.05 Design a Website for Server Side Processing
## Date:15.04.24

## AIM:
To design a website to find surface area of a Right Cylinder in server side.

## FORMULA:
Surface Area = 2Πrh + 2Πr<sup>2</sup>
<br>r --> Radius of Right Cylinder
<br>h --> Height of Right Cylinder

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
Register No: 212223230212

Name: SREE HARI K


### math.html:
~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
     rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh
     0JMhjY6hW+ALEwIH" crossorigin="anonymous">
</head>
<body style="background-color: yellowgreen ;padding-top: 12%;">
    <form action="" method="post">
        {% csrf_token %}
        <div class="card mx-auto text-center" style="width: 30rem;">
            <div class="card-header bg-primary text-white">
                Surface Area of Right Cylinder
            </div>
            <div class="card-body" style="background-color: yellow;">
                Enter the radius (in 'm') :
                <p><input type="text" name="r" id="" value="{{r}}"></p>
                Enter the height (in 'm') :
                <p><input type="text" name="h" id="" value="{{h}}"></p>
                <p><input class= "btn btn-primary" type="submit" value="Calculate Area"></p>
                The area (in 'm<sup>2</sup>') :
                <p><input type="text" name="a" value="{{a}}" id="" readonly></p>
            </div>
        </div>
    </form>
    <div class="card mx-auto text-center" style="width: 30rem;
     background-color: rgb(13 110 253);color: white;">
        By - Meenu.S,212223230124
    </div>
</body>
</html>
~~~
### views.py:
~~~
from django.shortcuts import render
def calculateArea(request):
    a=r=h=0
    if request.method=='POST':
        r=int(request.POST['r'])
        h=int(request.POST['h'])
        a=round(2*22/7*r*h + 2*22/7*r*r,2)
        print('Radius:',r,'\nHeight:',h,'\nArea:',a)
    return render(request,'math.html',{'a':a,'r':r,'h':h})
~~~
### urls.py:
~~~
from django.contrib import admin
from django.urls import path
from ex5 import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('',views.calculateArea)
]

~~~

## SERVER SIDE PROCESSING:
![322421221-24b03c4d-ba0c-40ca-804f-a4f4fcdc8918](https://github.com/sreehari2315/MathServer/assets/139331590/c00aeb87-1b77-4a14-bf9f-ffbc3fbab1fb)


## HOMEPAGE:
![322545938-9cdacaf5-5533-41ce-af0e-d849c9880832](https://github.com/sreehari2315/MathServer/assets/139331590/adf10713-bef9-48bf-a916-ae6250ae99bd)




## RESULT:
The program for performing server side processing is completed successfully.
