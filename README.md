# Ex.05 Design a Website for Server Side Processing
# Date: 
22/12/2025
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
template: 

{% load static %}
<html>
    <head>
        <style>
            h1{
                font-style: italic;
                font-family: algerian;
                color:rgb(220, 122, 122);
            }
            label{
                font-family: "Franklin Gothic Medium";
                font-style: italic;
                font-size:20;
            }
            form{
                margin:auto;
                align:center;
                padding: 10px;
                background-color: blanchedalmond;
                border-radius: 20px;
            }
            img{
                display: block;
                width:20%;
                margin-left:auto;
                margin-right: auto;
                border-radius: 20px;
            }
        </style>
    </head>
   <body bgcolor="aquamarine">
        <h1 align="center" style="padding-bottom: 30px;">LAMP INFLAMENT POWER CALCULATOR</h1>
        <img src="{% static 'img1.png' %}" alt="mime" usemap="maap"><br><br>
        <form method="post" style="margin:0 auto;width:fit-content">
            {% csrf_token %}
            <label align="center" style="margin:auto">INTENSITY: </label>
            <input type="text" name="intensity" required><br><br>
            <label align="center" style="margin:auto">RESISTENCE: </label>
            <input type="text" name="resistence" required><br><br>
            <button type="submit">CALCULATE</button>
            <h2 >POWER: {{ power }}</h2>
        </form>
        
    </body>
</html>

views.py:

from django.shortcuts import render


def calculator(request):
    if request.method=="POST":
        intensity=float(request.POST.get("intensity"))
        resistence=float(request.POST.get("resistence"))
        power=(intensity**2)*resistence
        print(f"INTENSITY: {intensity},RESISTENCE: {resistence},POWER:{power:.2}")
        return render(request,"calculator.html",{'power':power})
    return render(request,"calculator.html")
# Create your views here.

```
# SERVER SIDE PROCESSING:
![alt text](<Screenshot 30-09-2025 18_48_09.png>)

# HOMEPAGE:
![alt text](<127.0.0.1_8000 - Personal - Microsoft​ Edge 30-09-2025 18_46_11.png>) 
![alt text](<127.0.0.1_8000 - Personal - Microsoft​ Edge 30-09-2025 18_46_16.png>) 
![alt text](<127.0.0.1_8000 - Personal - Microsoft​ Edge 30-09-2025 18_45_59.png>)


# RESULT:
The program for performing server side processing is completed successfully.
