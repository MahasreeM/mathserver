# Ex.05 Design a Website for Server Side Processing
# Date:12-11-2024
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
#math.html
<body style="background-color: rgb(149, 206, 225);">
    <center>
    <h1>Lamp Filament Power Calculator</h1>
</center>

    <center>
    <form method="post">
        {% csrf_token %}
        <label for="intensity">Intensity (in lumens):</label>
        <input type="number" id="intensity" name="intensity" required><br><br>
    
        <label for="resistance">Resistance (in ohms):</label>
        <input type="number" id="resistance" name="resistance" required><br><br>
    
        <button type="submit">Calculate Power</button>
    </form>
</center>
    </body>

#result.html

    <body style="background-color: beige;"
<center>
   <h1>Result</h1>
</center>

<center>
   <p>The power of the lamp filament is {{ power }} watts.</p>
</center>

#views.py

from django.shortcuts import render
def calculate_power(request):
    if request.method == 'POST':
        intensity = int(request.POST.get('intensity'))
        resistance = int(request.POST.get('resistance'))
        power = ((intensity)*(intensity))*resistance
        return render(request, 'result.html', {'power': power})
    return render(request, 'index.html')

#urls.py

from django.contrib import admin
from django.urls import path
from mathsapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('powerlamp/',views.powerlamp,name"powerlamp),
    path('', views.calculate_power, name='calculate_power'),
]
```

# SERVER SIDE PROCESSING:
# HOMEPAGE:
![Screenshot 2024-12-06 115610](https://github.com/user-attachments/assets/fb178984-cc52-4605-9614-3c9995db99fa)


![Screenshot 2024-12-06 115632](https://github.com/user-attachments/assets/e5ddd9be-0daf-43fa-8dd8-4011d3999b1b)

# RESULT:
The program for performing server side processing is completed successfully.
