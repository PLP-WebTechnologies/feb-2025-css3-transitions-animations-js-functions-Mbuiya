# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

STEP 1 Create a CSS Animation

/* Define a simple CSS animation */
@keyframes pulse {
  0% {
    transform: scale(1);
    opacity: 1;
  }
  50% {
    transform: scale(1.1);
    opacity: 0.7;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

/* Apply the animation to a button */
button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  border: none;
  background-color: #3498db;
  color: white;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #2980b9;
}

/* Class that triggers the pulse animation */
.pulse-animation {
  animation: pulse 1s ease-in-out infinite;
}

STEP 2 JavaScript to Trigger Animation and Store Preferences

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Animation with LocalStorage</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <button id="animateButton">Click Me!</button>

  <script>
    // Check if the animation preference is saved in localStorage
    const animationEnabled = localStorage.getItem('animationEnabled') === 'true';

    // Get the button element
    const button = document.getElementById('animateButton');

    // Function to trigger the animation
    function triggerAnimation() {
      if (animationEnabled) {
        button.classList.add('pulse-animation');
        
        // Remove the animation after it finishes
        setTimeout(() => {
          button.classList.remove('pulse-animation');
        }, 1000);  // Duration of the animation
      }
    }

    // Event listener for button click
    button.addEventListener('click', () => {
      // Trigger the animation on click
      triggerAnimation();

      // Toggle the animation preference in localStorage
      const newPreference = !animationEnabled;
      localStorage.setItem('animationEnabled', newPreference);
    });

    // Apply animation based on user preference on page load
    if (animationEnabled) {
      button.classList.add('pulse-animation');
    }
  </script>

</body>
</html>


Happy Coding! 💻✨
