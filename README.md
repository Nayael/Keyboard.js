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
        LEFT: myFunction,
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
        upKeys:   ['LEFT', 'Q'],
        right:    'RIGHT',
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
*The key codes are just an indication*  
  
    BACKSPACE   |   8         A    |   65       LEFT_WINDOW_KEY     |   91      NUM_LOCK        |   144
    TAB         |   9         B    |   66       RIGHT_WINDOW_KEY    |   92      SCROLL_LOCK     |   145
    ENTER       |   13        C    |   67       SELECT_KEY          |   93      SEMI_COLON      |   186
    SHIFT       |   16        D    |   68       NUMPAD_0            |   96      EQUAL_SIGN      |   187
    CTRL        |   17        E    |   69       NUMPAD_1            |   97      COMMA           |   188
    ALT         |   18        F    |   70       NUMPAD_2            |   98      DASH            |   189
    PAUSE_BREAK |   19        G    |   71       NUMPAD_3            |   99      PERIOD          |   190
    CAPS_LOCK   |   20        H    |   72       NUMPAD_4            |   100     FORWARD_SLASH   |   191
    ESCAPE      |   27        I    |   73       NUMPAD_5            |   101     GRAVE_ACCENT    |   192
    SPACE       |   32        J    |   74       NUMPAD_6            |   102     OPEN_BRACKET    |   219
    PAGE_UP     |   33        K    |   75       NUMPAD_7            |   103     BACK_SLASH      |   220
    PAGE_DOWN   |   34        L    |   76       NUMPAD_8            |   104     CLOSE_BRAKET    |   221
    END         |   35        M    |   77       NUMPAD_9            |   105     SINGLE_QUOTE    |   222
    HOME        |   36        N    |   78       MULTIPLY            |   106
    LEFT        |   37        O    |   79       ADD                 |   107
    UP          |   38        P    |   80       SUBTRACT            |   109
    RIGHT       |   39        Q    |   81       DECIMAL_POINT       |   110
    DOWN        |   40        R    |   82       DIVIDE              |   111
    INSERT      |   45        S    |   83       F1                  |   112
    DELETE      |   46        T    |   84       F2                  |   113
    KEY_0       |   48        U    |   85       F3                  |   114
    KEY_1       |   49        V    |   86       F4                  |   115
    KEY_2       |   50        W    |   87       F5                  |   116
    KEY_3       |   51        X    |   88       F6                  |   117
    KEY_4       |   52        Y    |   89       F7                  |   118
    KEY_5       |   53        Z    |   90       F8                  |   119
    KEY_6       |   54                          F9                  |   120
    KEY_7       |   55                          F10                 |   121
    KEY_8       |   56                          F11                 |   122
    KEY_9       |   57                          F12                 |   123
                      
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
  