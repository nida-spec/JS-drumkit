# JS-drumkit
The repository contains the following files:
- index.html: includes the HTML code as well as the JS enclosed in the <script> element
- style.css: has all the CSS style code
- "sounds" folder: includes audio files (in .wav format) of all the sounds used for the drumkit
- background images
  
The project uses vanilla JS to make a simple drumkit. 
Inside the <body> element in index.html, there is a <div> element with a class of "keys". This <div> element has nine children <div> elements that each represent one key input.
The children <div> elements have a "data-" attribute that is used to associate a particular keyboard key to their keycodes and then use that keycode to hook it up to the audio. The keycodes being used in the project have been taken from: https://keycode.info/. The "data-key=65" is being associated with the key of "A", the "data-key=83" is being associated with the key of "S" and so on.
Each key is enclosed in a <kbd> element which is used to define the keyboard input. It indicates the part of inline text which represents the user keyboard input.
Following the <div>, are the <audio> elements with each containing a sound in .wav format and having the corresponding "data-" attribute.
  
Inside the <script> element, there is an Event Listener for the event "keydown" and a callback function. Inside the callback function I have two constants. The constant "audio" represents each of the audio elements. The audio elements are selected with a .querySelector() and inside it I have used an attribute selector to get just the required keycode from the <audio> element. Similarly, in the second constant "animation", the <div> with the class of "key" is selected using the .querySelector() and an attribute selector is used to get the required keycode from that <div>. This constant will be used to add the CSS class of ".playing" to the <div> of "key".
  
Following the constants, I have rewinded the audio so that it can be played repeatedly when the key is pressed without having to wait for the audio to end first. 
I have used the DOM property of "classList" with the method .add() to add the CSS class of ".playing" to "animation". This CSS class adds a transform property, a border-color of yellow and box-shadow.
  
In order to remove that CSS class of "playing" after the key is pressed and the audio has played, I have used an Event Listener with an event of "transitionend" and a callback function "removeTransition". The "transitionend" event is fired when a CSS transition has completed. Inside the callback function "removeTransition", I have removed the ".playing" CSS class by again using the DOM property "classList" but with the method .remove(). This will remove the ".playing" CSS class after .07s from the <div> elements with class "key" that have all been stored in the constant "keys" by using the .querySelectorAll() method.

  
The project was done by me when I found it in the "Practice" section of the DOM Manipulation Foundations in The Odin Project. 
  
