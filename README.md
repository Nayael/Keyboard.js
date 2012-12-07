Keyboard.js
==============
*This library allows you to easily handle all the keyboard events on your page.*
*You can also use it to control an object with the keyboard (adapted for video games)*

## Basic use ##
You can add event listeners on your keys by using the `addKeyListener()` method  

    Keyboard.addKeyListener('keydown', 'P', function () {
        console.log('P was pressed');  
    });  
    Keyboard.addKeyListener('keyup', 'BACKSPACE', function () {  
        console.log('BACKSPACE was released');  
    });
*You can find a* [list of all the keys](#keys-list) *on the bottom of the page*
  
## Advanced use ##
If you want to associate specific controls to an object, you can define a `controls` property on your object
  
    obj.controls = {
        LEFT_ARROW: myFunction,
        SHIFT: myFunction2,
        TAB: myFunction3
    };

And call the `makeControllable()` method

    Keyboard.makeControllable(obj); // Making the object controllable with the Keyboard
  
Then, call the `checkControls()` method on your object to apply the pressed keys (in your game main loop for instance)
  
    window.requestAnimationFrame = function() {
        obj.checkControls();
    }
  
## Advanced Configuration ##
Instead of using the default keys labels *(see [keys list](#keys-list))*, you can define your own labels, affected to one or several keys.  
In order to do that, use the `bindKeys()` method. You can use an array or a string to define a match:
  
    Keyboard.bindKeys({
        upKeys:   ['LEFT_ARROW', 'Q'],
        right:    'RIGHT_ARROW',
        submitKeys: ['ENTER', 'ESCAPE']
    });
  
Then use them like regular keys with the other methods:
  
    obj.controls = {
        upKeys: myFunction,
        right: myFunction2,
        submitKeys: myFunction3,
        KEY_1: myFunction4,
        P: myFunction5
    };
  
## Keys list ##
  
    BACKSPACE   |   A   |   LEFT_WINDOW_KEY     |    NUM_LOCK     
    TAB         |   B   |   RIGHT_WINDOW_KEY    |    SCROLL_LOCK  
    ENTER       |   C   |   SELECT_KEY          |    SEMI_COLON   
    SHIFT       |   D   |   NUMPAD_0            |    EQUAL_SIGN   
    CTRL        |   E   |   NUMPAD_1            |    COMMA        
    ALT         |   F   |   NUMPAD_2            |    DASH         
    PAUSE_BREAK |   G   |   NUMPAD_3            |    PERIOD       
    CAPS_LOCK   |   H   |   NUMPAD_4            |    FORWARD_SLASH
    ESCAPE      |   I   |   NUMPAD_5            |    GRAVE_ACCENT 
    SPACE       |   J   |   NUMPAD_6            |    OPEN_BRACKET 
    PAGE_UP     |   K   |   NUMPAD_7            |    BACK_SLASH   
    PAGE_DOWN   |   L   |   NUMPAD_8            |    CLOSE_BRAKET 
    END         |   M   |   NUMPAD_9            |    SINGLE_QUOTE 
    HOME        |   N   |   MULTIPLY            |
    LEFT_ARROW  |   O   |   ADD                 |
    UP_ARROW    |   P   |   SUBTRACT            |
    RIGHT_ARROW |   Q   |   DECIMAL_POINT       |
    DOWN_ARROW  |   R   |   DIVIDE              |
    INSERT      |   S   |   F1                  |
    DELETE      |   T   |   F2                  |
    KEY_0       |   U   |   F3                  |
    KEY_1       |   V   |   F4                  |
    KEY_2       |   W   |   F5                  |
    KEY_3       |   X   |   F6                  |
    KEY_4       |   Y   |   F7                  |
    KEY_5       |   Z   |   F8                  |
    KEY_6       |           F9                  |
    KEY_7       |           F10                 |
    KEY_8       |           F11                 |
    KEY_9       |           F12                 |