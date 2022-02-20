# Design a Website for Server Side Processing

## AIM:
To design a website to perform mathematical calculations in server side.

## DESIGN STEPS:

### Step 1:
Requirement collection.

### Step 2:
Creating the layout using HTML and CSS for performing calculation.

### Step 3:
Write views.py to get values and render it in server side.

### Step 4:
Add your created app in settings.py.

### Step 5:
Run the server.

### Step 6:
Publish the website in the given URL.

## PROGRAM :

### HTML CODING:
### area.html:
```
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <title>Page Title</title>
    <meta name='viewport' content='width=device-width, initial-scale=1'>
    
</head>
<style>
    *{
        box-sizing: border-box;
        font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif
    }
    body{
    background-color: rgb(183, 44, 238);
    }

    .container{
    width: 1080px;
    height: 350px;
    margin-top: 100px;
    margin-left: auto;
    margin-right: auto;
    border-radius: 25px;
    border: 10px solid rgba(151, 92, 117, 0);
    box-shadow: inset 0 0 15px rgb(86, 6, 161);
    background-color:rgb(188, 133, 240);
    }
    h1{
        text-align: center;
        padding-top: 15px;
    }
    .calculate{
        padding-top: 10px;
        padding-bottom: 10px;
        padding-left: 10px;
        padding-right:10px;
        text-align: center;
        font-size: 20px;
    }
</style>
<body>
    <div class="container">
        <h1>AREA OF A RECTANGLE</h1>
        <form method="POST">
            <div class="calculate"> 
                Base:<input type="text" name="base" value=></input><br/>
            </div>
            <div class="calculate">
                Height:<input type="text" name="height" value=></input><br/>
            </div>
            <div class="calculate">
                <input type="submit" value="Calculatearea"></input><br/>
            </div>
            <div class="calculate">
                Area:<input type="text" name="area" value=></input>
            </div>
        </form>
    </div>
</body>
```
### views.py:
```
from django.shortcuts import render

def areacalculation(request):
    context ={}
    context["area"]='0'
    context["b"]='0'
    context["h"]='0'
    if request.method == 'POST':
        
        l=request.POST.get('base','0')
        b=request.POST.get('height','0')
        area=int(l)*int(b)
        context['area'] = area
        context['b']=b
        context['h']=h
    return render(request,"mathapp/area.html",context)
```    
 ### urls.py  
 ```
 from django.urls import path
from mathapp import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('areaofrectangle/',views.areacalculation,name="areaofrectangle"),
    path('',views.areacalculation,name="areaofrectangle")
]
```
## OUTPUT:

<img width="863" alt="n1" src="https://user-images.githubusercontent.com/94294872/154849809-24f3566e-491d-44d9-a8fd-f3265d7db322.png">

## Result:
Hence a website is designed to perform mathematical calculations in server side.
