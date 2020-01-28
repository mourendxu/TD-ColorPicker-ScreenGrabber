# TD-ColorPicker-ScreenGrabber
 ![alt text](https://github.com/mourendxu/TD-ColorPicker-ScreenGrabber/blob/master/ScreenGrabber1.0.jpg "Screen Grabber Screen Shot")
 
 Touchdesigner TOX for Picking Color and Grabbing Screen Shots
 
 This TOX uses a custom Mouse In CHOP to work across desktops and outside of Touch's window. Touchdesigner must be the active application for this to work.

[Please find more info on how to install Custom Operators here](https://docs.derivative.ca/Custom_Operators#Using_Custom_OPs_-_Plugin_Folder_Locations)

 
 This TOX only works on Windows. To make it work on Mac, you will either need to write a similar Mouse In CHOP for Mac or use Python to achieve something that's some what equivalent. You basically need to grab the coordinates of your mouse with respect to all your desktops as a single space.
 
 The only difference between the color picking mode and the screen grabbing mode is if you move the mouse while holding down the *Control* key.
 
 ## Usage:
 
 To use this TOX:
 1. Copy the tox into your project directory, in the same folder as your project toe file.
 2. Copy the MouseInAltCHOP.dll into your *Plugins* directory, either your system level *Plugins* folder or your project level *Plugins* folder.
 [For details on Plugins/Custom Operators, Click here](https://docs.derivative.ca/Custom_Operators#Using_Custom_OPs_-_Plugin_Folder_Locations)
 3. Restart Touchdesigner, so, it can load the MouseInAltCHOP into memory.
 4. Drag and Drop *ScreenGrab.tox* into your project.
 
 ### Cancelling
 
 During any of the following operations, before you let go the *Control* key, you can cancel the operation by pressing the *Shift* key.
 
 ### Picking Color:
 
 1. Activate the Tox by clicking on the *On/Off* Toggle, under *Settings*
 2. Right click on the Tox, and select *View*
 3. Mouse over the color you want to pick. *Note: Make sure the color is the one you are looking for by checking the Viewer you opened in Step 2. Due to the fact that this component is pixel accurate, you may actually be mousing over the anti-aliased edge color. Always verify the color in the viewer.*
 4. Press and Release the *Control* key. **DO NOT MOVE THE MOUSE** during this. 
 
 The colors you picked will be outputted to output 2 and 3. Output 2 gives you the colors in a DAT, with the RGBA values. You can easily take this and generate a color table for a RampTOP. Output 3 gives you the color(s) as a single image, laid out in a grid.
 
 
 
 ### Grabbing a Screen Shot
 
 1. Activate the Tox by clicking on the *On/Off* Toggle, under *Settings*
 2. Right click on the Tox, and select *View*
 3. Move your mouse to one of the corners of the area you want to capture.
 4. Press and **HOLD** the *Control* key. 
 5. Move your mouse to the opposite(diagonally) corner of the area you want to capture.
 6. Let go of the *Control* key.
 
 You can select the images you have captured with the *Screen Shot Output Index* slider under the *Settings* page.
 
 
 
 ## Parameter and Outputs
 
 ### Parameter/Settings
 
 * On/Off - This turns the component On and Off. In Off, the ScreenGrab TOP and Control key capturing are turned off. *It's recommended to leave it on Off when not using, considering how often the Control key can be pressed while using Touchdesigner.*
 
 * Total Screeen Shots - This is a read-only parameter. This parameter simply reflects the number of inputs to the switch TOP. You can use this parameter to trigger things like, auto save last captured screenshot, etc.
 
 * Screen Shot Output Index - This parameter is bound to the switch TOP inside of the component. By default, it will display the last captured screen shot. But you can use it to display any of the screen shots that you have captured so far.
 
 * Clear* - Self explanatory. 
 
 
 
 ### Outputs
 
 * Output 1 TOP - One of the captured screen shots. Selectable using the *Screen Shot Output Index* slider.
 
 * Output 2 DAT - All of the picked colors so far in a table. Listing their RGBAs. You can attach a position column to this, and you can use it directly in a Ramp TOP.
 
 * Output 3 TOP - All of the picked colors so far, laid out in a grid.
 
 
 
