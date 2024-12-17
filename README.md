# Ex.05 Design a Website for Server Side Processing
## Date:13/12/2024

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side. 


## FORMULA:
P = I<sup>2</sup>R
<br> P --> Power (in watts)
<br> I --> Intensity
<br> R --> Resistance

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
```
<html>
<head>
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=brave'>
<title>Power</title>
<meta name='viewport' content='width=device-width, initial-scale=1'>
<style type="text/css">
body {
    background-color:  turquoise;
}
.edge {
    width: 100%;
    padding-top: 250px;
    text-align: center;
}
.box {
    display: inline-block;
    border: thick double rgb(59, 8, 116);
    width: 500px;
    min-height: 300px;
    font-size: 20px;
    background-color: azure;
}
.formelt {
    color: black;
    text-align: center;
    margin-top: 7px;
    margin-bottom: 6px;
}
h1 {
    color: black;
    padding-top: 20px;
}
</style>
</head>
<body>
<div class="edge">
    <div class="box">
        <h1>Power</h1>
        <form method="POST">
            {% csrf_token %}
            <div class="formelt">


 Intensity (I): <input type="text" name="Intensity" value="{{Intensity}}"> w/m2<br/>
            </div>
            <div class="formelt">
                Resistance (R): <input type="text" name="Resistance" value="{{Resistance}}"> Ω<br/>
            </div>
            <div class="formelt">
                <input type="submit" value="Calculate"><br/>
            </div>
            <div class="formelt">
                Power (P): <input type="text" name="Power" value="{{Power}}"> W<br/>
            </div>
        </form>
    </div>
</div>
</body>
</html>

```
urls.py
```
from django.contrib import admin
from django.urls import path
from . import views  # Ensure views is imported correctly

urlpatterns = [
    path('admin/', admin.site.urls),
    path('Power/', views.Power, name="Power"),
    path('mathapp', views.Power, name="home"), 
]

```
views.py
```
from django.shortcuts import render

def Power(request):
    context = {}
    context['Power'] = "0"
    context['I'] = "0"
    context['R'] = "0"

    if request.method == 'POST':
        print("POST method is used")
        I = request.POST.get('Intensity', '0')
        R = request.POST.get('Resistance', '0')
        print('request =', request)
        print('Intensity =', I)
        print('Resistance =', R)

        try:
            # Convert I and R to integers and calculate Power
            I = int(I)
            R = int(R)
            Power = (I * I) * R
            context['Power'] = Power
        except ValueError:
            # Handle invalid input gracefully
            context['Power'] = "Invalid Input"
            print("Error: Non-integer values submitted!")

        context['I'] = I
        context['R'] = R
        print('Power =', context['Power'])

    return render(request, 'mathapp/maths.html', context)

```


## HOMEPAGE:
![image](https://github.com/user-attachments/assets/0b1a34b5-2e0c-496d-81d5-e0d4cf433051)




## SERVER SIDE PROCESSING:
![image](https://github.com/user-attachments/assets/96384adf-3183-41eb-b871-68869c7d92c6)


## RESULT:
The program for performing server side processing is completed successfully.
