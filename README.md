# Ex.08 Design of Interactive Image Gallery
# Date:10-05-2025
# AIM:
To design a web application for an inteactive image gallery with minimum five images.

# DESIGN STEPS:
## Step 1:
Clone the github repository and create Django admin interface.

## Step 2:
Change settings.py file to allow request from all hosts.

## Step 3:
Use CSS for positioning and styling.

## Step 4:
Write JavaScript program for implementing interactivity.

## Step 5:
Validate the HTML and CSS code.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
<html>
    <head>
        <style>
            body{
                background-image: url(bg1.avif);
                display: flex;
                justify-content: center;
                
            }
            .title{
                text-align: center;
                font-size: 140px;
                left: 1800px;
                position: absolute;
                color: whitesmoke;
                text-shadow: 0 0 5px #212020,
                 0 0 15px #1a1717;
                top: 100px;
                font-style: italic;
            }
            .gallery-item1{
                
               width: 70px;
               height: 50px;
                position: absolute;
                top: 300px;
                left: 150px;
            }
            .gallery-item1 img:hover {
            transform: scale(1.30);
            cursor: all-scroll;
        }
            .item2 img {
                height: 900px;
                width: 500px;
                position: absolute;
                top: 500px;
                left: 850px;
            }
            .item2 img:hover {
            transform: scale(1.30);
            cursor: all-scroll;
        }
            .lastline{
                text-align: center;
                font-style: italic;
                font-size: 40px;
                color: white;
                top: 2245px;
                position: absolute;
                left: 2000px;
               
            }
            .item3 img{
                height: 900px;
                width: 500px;
                position: absolute;
                top: 500px;
                left:1580px;
            }
            .item3 img:hover {
            transform: scale(1.30);
            cursor: all-scroll;
        }
            .item4 img{
                height: 900px;
                width: 500px;
                position: absolute;
                top: 500px;
                left: 2290px;
            }
            .item4 img:hover {
            transform: scale(1.30);
            cursor: all-scroll;
        }
            .item6 img{
                height: 900px;
                width: 500px;
                position: absolute;
                top: 500px;
                left: 3000px;
            }
            .item6 img:hover {
            transform: scale(1.30);
            cursor: all-scroll;
        }
            .item5 img{
                height: 900px;
                width: 500px;
                position: absolute;
                top: 500px;
                left: 3800px;
        }
        .item5 img:hover {
            transform: scale(1.30);
            cursor: all-scroll;
        }
        .content.blur {
         filter: blur(8px); 
         transition: filter 0.3s ease; 
         
        }

        .slider {
            display: none;
            position: fixed;
            z-index: 10;
            left: 0;
            top: 50%;
            transform: translateY(-50%);
            width: 100%;
            text-align: center;
            background-color: rgba(0, 0, 0, 0.8);
        }

        .slider img {
            width: 1000px;
            border-radius: 70px;
            transition: opacity 0.10s ease-in;
        }

        .arrow {
            cursor: all-scroll;
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            font-size: 40px;
            color:black;
            user-select: none;
            padding: 10px;
        }

        .arrow.left {
            left: 10px;
            color: whitesmoke;
            
        }

        .arrow.right {
            right: 10px;
            color: whitesmoke;
        }

        .arrow:hover {
            color: gold;
            size: 50px;
        }

        close-btn {
            position: absolute;
            top: 20px;
            right: 20px;
            background-color: rgba(0, 0, 0, 0.6);
            color: rgb(0, 255, 251);
            font-size: 100px;
            cursor: all-scroll;
            transition: background-color 0.3s ease;
            border-radius: 5px;
            display: block;
        }

        close-btn:hover {
            background-color: rgba(0, 0, 0, 0.8);
        }
        </style>

    </head>
    <body>
        <div class="content">
        <div class="title">IMAGE GALLERY </div>

        <div class="gallery-container">

                    <div class="item1">
                        <img src="C:\Users\admin\Downloads\a.jpg">
                    </div>
                    
                    <div class="item2">
                        <img src="C:\Users\admin\Pictures\Screenshots\b.png">
                    </div>  
                    <div class="item3">
                        <img src="C:\Users\admin\Downloads\c.jpg">
                    </div>  
                    <div class="item4">
                        <img src="C:\Users\admin\Downloads\d.avif">
                    </div>  
                    <div class="item6">
                        <img src="C:\Users\admin\Downloads\e.jpg">
                    </div>  
                    <div class="item5">
                        <img src="C:\Users\admin\Downloads\f.jpeg">
                    </div>  
                    <footer class="lastline">
                        <p>&capbrcup; <b>DESIGNED BY JAYASURYA B</b></p>
                    </footer>

            </div>
    </div>
        <div class="slider" id="slider">
           
            <button class="close-btn" id="close-btn">&#10006;</button>
            <span class="arrow left" id="prev">&#10094;</span>
            <img src="im1.JPG" alt="Slider Image" id="slider-img">
            <span class="arrow right" id="next">&#10095;</span>
        </div>

        <script>
            document.addEventListener("DOMContentLoaded", function () {
    const galleryItems = document.querySelectorAll(".gallery-container img");
    const slider = document.getElementById("slider");
    const sliderImg = document.getElementById("slider-img");
    const closeBtn = document.getElementById("close-btn");
    const prev = document.getElementById("prev");
    const next = document.getElementById("next");

    let currentIndex = 0;

    
    galleryItems.forEach((item, index) => {
        item.addEventListener("click", () => {
            slider.style.display = "block";
            sliderImg.src = item.src;
            currentIndex = index;
            content.classList.add("blur");
        });
    });

    
    closeBtn.addEventListener("click", () => {
        slider.style.display = "none";
        content.classList.remove("blur");
    });

    
    prev.addEventListener("click", () => {
        currentIndex = (currentIndex - 1 + galleryItems.length) % galleryItems.length;
        sliderImg.src = galleryItems[currentIndex].src;
    });

    
    next.addEventListener("click", () => {
        currentIndex = (currentIndex + 1) % galleryItems.length;
        sliderImg.src = galleryItems[currentIndex].src;
    });

    slider.addEventListener("click", (e) => {
        if (e.target === slider || e.target === closeBtn) {
            slider.style.display = "none";
        }
    });

    document.addEventListener("keydown", (e) => {
        if (slider.style.display === "block") {
            if (e.key === "ArrowLeft") {
                prev.click();
            } else if (e.key === "ArrowRight") {
                next.click();
            } else if (e.key === "Escape") {
                closeBtn.click();
            }
        }
    });
});

        </script>

    </body>
</html>

```
# OUTPUT:

![Screenshot 2025-05-12 222249](https://github.com/user-attachments/assets/35486d54-549a-4ee5-9e63-d28af9917fa1)

![Screenshot 2025-05-12 222307](https://github.com/user-attachments/assets/5ecc76fd-e00a-4ee3-bcdd-d79e7a46f018)

![Screenshot 2025-05-12 222350](https://github.com/user-attachments/assets/bdee4578-56ce-4b44-808b-3efc13525a90)


# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
