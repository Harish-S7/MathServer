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


## HOMEPAGE:
![image](https://github.com/user-attachments/assets/1eb173be-2846-430f-a127-e3f5b37600a3)



## SERVER SIDE PROCESSING:
![Screenshot (40)](https://github.com/user-attachments/assets/d4e5442a-0e4e-4f6b-8785-869231ebdb2a)

## RESULT:
The program for performing server side processing is completed successfully.
