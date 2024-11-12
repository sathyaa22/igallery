# Ex.08 Design of Interactive Image Gallery
## Date:

## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :

### HTML
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Image Gallery</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <!-- Gallery Heading -->
  <h1 class="gallery-heading">Interactive Image Gallery</h1>

  <!-- Image Gallery -->
  <div class="gallery">
    <div class="gallery-item">
      <img src="six.jpg" alt="Image 1" class="gallery-img">
      <div class="image-name">Juice</div> <!-- Name for Image 1 -->
    </div>
    <div class="gallery-item">
      <img src="seven.jpg" alt="Image 2" class="gallery-img">
      <div class="image-name">Coffee</div> <!-- Name for Image 2 -->
    </div>
    <div class="gallery-item">
      <img src="three.jpg" alt="Image 3" class="gallery-img">
      <div class="image-name">Honey</div> <!-- Name for Image 3 -->
    </div>
    <div class="gallery-item">
      <img src="four.jpg" alt="Image 4" class="gallery-img">
      <div class="image-name">Puppy</div> <!-- Name for Image 4 -->
    </div>
    <div class="gallery-item">
      <img src="five.jpg" alt="Image 5" class="gallery-img">
      <div class="image-name">Forest</div> <!-- Name for Image 5 -->
    </div>
    <div class="gallery-item">
      <img src="one.jpg" alt="Image 6" class="gallery-img">
      <div class="image-name">French</div> <!-- Name for Image 6 -->
    </div>
    <div class="gallery-item">
      <img src="amaran.jpg" alt="Image 7" class="gallery-img">
      <div class="image-name">Army</div> <!-- Name for Image 7 -->
    </div>
    <div class="gallery-item">
      <img src="dog.jpeg" alt="Image 8" class="gallery-img">
      <div class="image-name">Dog</div> <!-- Name for Image 8 -->
    </div>
    <div class="gallery-item">
      <img src="ten.jpg" alt="Image 9" class="gallery-img">
      <div class="image-name">Monument</div> <!-- Name for Image 9 -->
    </div>
    <div class="gallery-item">
      <img src="ok.jpg" alt="Image 10" class="gallery-img">
      <div class="image-name">Black coffee</div> <!-- Name for Image 10 -->
    </div>
  </div>

  <!-- Modal for Enlarged Image -->
  <div id="modal" class="modal">
    <span class="close-btn" onclick="closeModal()">&times;</span>
    <img id="modal-img" src="" alt="Enlarged Image">
  </div>

  <script src="script.js"></script>
</body>
</html>
```

### CSS
```
CSS

/* Global Styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    text-align: center;
}

.gallery-heading {
    margin: 20px 0;
    font-size: 2.5em;
    color: #333;
}

/* Gallery Container */
.gallery {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 15px;
    padding: 20px;
    max-width: 1100px;
    margin: 0 auto;
}

/* Gallery Item Styles */
.gallery-item {
    position: relative;
    overflow: hidden; /* Ensure the text doesn't overflow outside the image */
}

.gallery-img {
    width: 100%;
    height: 200px; /* Fixed height */
    object-fit: cover; /* Ensure images cover the area without stretching */
    border-radius: 10px;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    cursor: pointer;
}

.gallery-img:hover {
    transform: scale(1.05);
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

/* Image Name Styles */
.image-name {
    position: absolute;
    bottom: 10px; /* Position the text near the bottom */
    left: 50%;
    transform: translateX(-50%); /* Center the text horizontally */
    color: white;
    font-size: 18px;
    font-weight: bold;
    background-color: rgba(0, 0, 0, 0.6); /* Semi-transparent background */
    padding: 5px 10px;
    border-radius: 5px;
    opacity: 0; /* Start with hidden text */
    transition: opacity 0.3s ease; /* Smooth fade-in effect */
}

.gallery-item:hover .image-name {
    opacity: 1; /* Show the text when hovering */
}

/* Modal Styles */
.modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.8);
    display: none;
    justify-content: center;
    align-items: center;
}

.modal img {
    max-width: 90%;
    max-height: 90%;
    object-fit: contain; /* Ensure the modal image fits within the screen without distortion */
}

.close-btn {
    position: absolute;
    top: 20px;
    right: 20px;
    color: white;
    font-size: 30px;
    cursor: pointer;
}
```

### JS
```
JS
const galleryImages = document.querySelectorAll('.gallery-img');

const modal = document.getElementById('modal');
const modalImg = document.getElementById('modal-img');

function openModal(event) {
    modalImg.src = event.target.src;

    modal.style.display = 'flex';
}

function closeModal() {
    modal.style.display = 'none';
}

galleryImages.forEach(image => {
    image.addEventListener('click', openModal);
});

const closeButton = document.querySelector('.close-btn');
closeButton.addEventListener('click', closeModal);

modal.addEventListener('click', (event) => {
    if (event.target === modal) {
        closeModal();
    }
});
```

## OUTPUT:

![image](https://github.com/user-attachments/assets/b1db83ea-1ac6-4d68-b7f6-354c6f8bc349)


## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
