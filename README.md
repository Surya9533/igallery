# Ex.08 Design of Interactive Image Gallery
## Date:07.05.2025

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
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Photo Gallery</title>
    <link rel="stylesheet" href="styles.css"> <!-- Link to CSS -->
</head>
<body>
    <div id="gallery-container"></div>

    <div id="overlay" class="hidden">
        <img id="overlay-image" src="" alt="Large view">
        <button id="close-button">&times;</button>
    </div>

    <!-- Footer -->
    <footer>
        <p> Designed and developed by RAHUL RIO S</p>
    </footer>

    <script src="gallery.js"></script> <!-- Link to JavaScript -->
</body>
</html>

// List of image paths (Replace with your own images)
const photoPaths = [
    'itachi.jpeg', 'hulk.jpeg', 'thor.jpeg', 'wanda.jpeg', 'doctor.jpeg',
    'ironman.jpeg', 'spiderman.jpeg', 'mj.jpeg', 'superman.jpeg', 'Captain America.jpeg'
];

// Get references to the gallery container and overlay elements
const galleryContainer = document.getElementById('gallery-container');
const overlay = document.getElementById('overlay');
const overlayImage = document.getElementById('overlay-image');
const closeButton = document.getElementById('close-button');

// Create image elements for the gallery
photoPaths.forEach(photo => {
    const img = document.createElement('img');
    img.src = photo;
    img.alt = 'Gallery Image';
    img.addEventListener('click', () => {
        overlayImage.src = photo; // Set overlay image source
        overlay.classList.remove('hidden'); // Show overlay
    });
    galleryContainer.appendChild(img);
});

// Close overlay when close button is clicked
closeButton.addEventListener('click', () => {
    overlay.classList.add('hidden'); // Hide overlay
});

// Close overlay when clicking outside the image
overlay.addEventListener('click', (event) => {
    if (event.target === overlay) {
        overlay.classList.add('hidden');
    }
});


/* Reset default styles */
body, html {
    margin: 0;
    padding: 0;
    overflow: hidden;
}

/* Background image */
body {
    background-image: url('Ultimato.jpeg'); /* Replace with your background image */
    background-size: cover;
    background-position: center;
}

/* Gallery container */
#gallery-container {
    display: grid;
    grid-template-columns: repeat(5, 1fr); /* 5 photos per row */
    gap: 10px;
    margin: 20px;
    padding: 20px;
    border-radius: 10px;
    overflow-y: auto; /* Allow scrolling if necessary */
    height: calc(100vh - 40px); /* Fullscreen minus padding */
    box-shadow: 0 0 10px rgba(176, 155, 155, 0.3);
}

/* Individual photos */
#gallery-container img {
    width: 75%;
    height: auto;
    border-radius: 5px;
    transition: transform 0.3s;
    cursor: pointer;
}

#gallery-container img:hover {
    transform: scale(1.1);
}

/* Overlay for enlarged photo */
#overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.8);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1000;
}

#overlay img {
    max-width: 70%;
    max-height: 75%;
    border-radius: 10px;
    box-shadow: 0 0 20px rgba(255, 255, 255, 0.5);
}

#overlay.hidden {
    display: none;
}

#close-button {
    position: absolute;
    top: 10px;
    right: 10px;
    font-size: 2rem;
    color: white;
    background: transparent;
    border: none;
    cursor: pointer;
    z-index: 1100;
}
footer {
    position: fixed; /* Keeps the footer at the bottom of the screen */
    bottom: 0;
    left: 0;
    width: 100%; /* Stretches footer across the page */
    background-color: rgba(0, 0, 0, 0.8);
    color: white;
    text-align: center;
    padding: 10px 0;
    font-size: 1rem;
    z-index: 1000; /* Ensures it appears above other elements */
}

footer p {
    margin: 0;
}

```

## OUTPUT:
![image](https://github.com/user-attachments/assets/f3ab9ce9-0e22-4943-a15d-b1996a45cab1)



## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
