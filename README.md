Keyboard.js
==============
*This library allows you to easily handle all the keyboard events on your page.*
*You can also use it to control an object with the keyboard (adapted for video games)*

## Basic use ##
You can add event listeners on your keys by using the `addKeyListener()` method  

    Keyboard.addKeyListener('keydown', 'P', function () {
        console.log('The key P is pressed');  
    });  
    Keyboard.addKeyListener('keyup', 'BACKSPACE', function () {  
        console.log('The key BACKSPACE was released');  
    });
