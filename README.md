# CircuitPython_MLX90640_PyGamer_Plus
Enhanced version of thermal camera example with PyGamer and MLX90640


I wrote mlx90640_pygamer.py based on mlx90640_simpletest.py from https://github.com/adafruit/Adafruit_CircuitPython_MLX90640
And the example code is advertised on this learn guide from @adafruit: https://learn.adafruit.com/adafruit-mlx90640-ir-thermal-camera/circuitpython-thermal-camera

Improvement already implemented:
* Compute and display the average temperature of the center of the sensor
* Indicate the lowest pixel with an O
* Indicate the highest pixel with an X
* Use existing FancyLED library rather than the gradiant code

Possible improvement not implemented yet:
* Make a PyPortal version that accomodate the bigger screen
* Use the button and joystic from the PyGamer to provide a user interface and a few feature:
   * freeze / unfreeze the screen
   * save the image on an SD card ( https://learn.adafruit.com/saving-bitmap-screenshots-in-circuitpython )
   * enable / disable 
   * switch between auto-scale and manual scale with lowest / highest temperature
   * [require AirLift Feather Wing] send image over wifi (not even a clue on how to do that)

mlx90640_pygamer_plus+sd.py now record the 32*24 bitmap after 30 frames and the full screen after 60 frames.
This produce the picture.bmp and screen.bmp.

I believe there is a bug in save_pixels from adafruit_bitmapsaver as the screen.bmp does not match what I see on the screen:
1) The last column of pixel from the picture are duplicated to the edge.
2) The three temperature (min, center, max) are not text but colour blob.


