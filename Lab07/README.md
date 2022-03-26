## Lab 7

Learn tutorial: https://nerdparadise.com/programming/pygame:
      * Getting Started
      * Working with Images
      * Music and Sound Effects
      * Geometric Drawing
      * Fonts and Text
      * More on Input

1. Create a simple clock application (only with minutes and seconds) which is synchronized with system clock. Use Mickey's right hand as minutes arrow and left - as seconds. For moving Mickey's hands you can use:
      ```pygame.transform.rotate```
more explanation: https://stackoverflow.com/a/54714144 


   <img src="images/mickeyclock.jpeg" alt="mickeyclock" style="width:280px;height:210px;" />
2. Create music player with keyboard controller. You have to be able to press keyboard: play, stop, next and previous as some keys. Player has to react to the given command appropriately.
3. Draw circle - a red ball of size 50 x 50 (radius = 25) on white background. When user presses Up, Down, Left, Right arrow keys on keyboard, the ball should move by 20 pixels in the direction of pressed key. The ball should not leave the screen, i.e. user input that leads the ball to leave of the screen should be ignored
