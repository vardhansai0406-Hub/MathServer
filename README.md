# Ex.04 Design a Website for Server Side Processing
## Date:28/12/2025

## AIM:
To create a web page to calculate vehicle mileage and fuel efficiency using server-side scripts.

## FORMULA:
M = D / F
<br> M --> Mileage (in km/l)
<br> D --> Distance Travelled (in km)
<br> F --> Fuel Consumed (in l)

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

## PROGRAM:
```
math.html

<html>
    <head>
        <title>Fuel Efficiency</title>
    </head>
    <style>
        .box
        {
            margin-top: 20%;
            margin-left: 25%;
            margin-right:25%;
            border: px solid rgb(0, 255, 191); 
            background-color: rgb(34, 0, 255);
            text-align: center; 
        }
    </style>
    <body>
        <div class="box">
        <h1>Fuel Efficiency Calculator</h1>
        <h3>VARDHANSAI I </h3>
        <h3>25015695</h3>
        <br>
        <form method="POST">
            {% csrf_token %}
            <br>
            <label>Distance Travelled: </label>
            <input type="text" name="distance" value="{{d}}" required> Km
            <br>
            \<br>
            <label>Fuel Consumed: </label>
            <input type="text" name="fuel" value="{{f}}" required> L
            <br>
            <br>
            <input type="submit" value="Calculate">
            <br>
            <br>
            <label>Fuel Efficiency: </label>
            <input type="text" name="mileage" value="{{mileage}}"> Km/L
            <br>
        </form>
        </div>
    </body>
</html>

views.py

from django.shortcuts import render
def mileage(request):
    d = int(request.POST.get('distance', 0))
    f = int(request.POST.get('fuel', 0))
    mileage = d/f if request.method == 'POST' else 0
    print("distance",d)
    print("fuel",f)
    print("mileage",mileage)
    return render(request, 'mathapp/math.html', {'d': d, 'f': f, 'mileage':mileage})

urls.py

from django.urls import path
from mathapp import views
urlpatterns = [
    path('', views.mileage, name='mileage'),
]

```


## OUTPUT - SERVER SIDE:
![alt text](<Screenshot (17).png>)

## OUTPUT - WEBPAGE:
![alt text](<Screenshot (16).png>)

## RESULT:
The a web page to calculate vehicle mileage and fuel efficiency using server-side scripts is created successfully.
