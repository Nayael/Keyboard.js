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
  
## Advanced use ##
If you want to associate specific controls to an object, you can define a `controls` property on your object
  
    this.controls = {
        LEFT: myFunction,
        SHIFT: myFunction2,
        TAB: myFunction3
    };

And call the `makeControllable()` method

    Keyboard.makeControllable(this); // Making the object controllable with the Keyboard
  
Then, call the `checkControls()` method on your object to apply the pressed keys (in your game main loop for instance)