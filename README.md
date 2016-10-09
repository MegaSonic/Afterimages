# Afterimages

This Component attempts to replicate an Afterimage effect present in games like Mega Man Zero, the 2D Castlevania games, and several others.

Put this Component on a moving GameObject with a Sprite Renderer, add a few lines of code, and watch some magic happen. NOTE: This code probably has some bugs, and is not optimized! (Though it will probably work pretty well for whatever you're planning to do with it)

Important functions for you:

StartImages: starts up the Afterimages effect. Afterimage sprites will appear out from behind the GameObject the component is on (based on Sprite Sorting Order), tracking the object's position. Calling StartImages while Afterimages are active will do nothing.

ForceStartImages: Like StartImages, but calling this while Afterimages are active will have them reset, having them trace back out from the main sprite.

StopImages: Causes Afterimages to pull back into the main GameObject, eventually turning off.

ForceStopImages: Immediately turns off the afterimages.

I recommend mainly using StartImages and StopImages.


Customizable options in the Component:

Images to Display: How many afterimages you want to render.

Image Color: If you want each afterimage to be one color, you can set it here.

Save Sprites: If off, Afterimages will only save positions and each afterimage will use the main GameObject's current sprite frame. Check this if you want Afterimages to also keep track of the sprite it was at that position. Works best if you have detailed animations.

Delay Between Images: How close together do you want images to be? Note that this runs based on the Update loop, and games will run at a higher framerate/Update rate in builds than in the editor, so you might notice images being a lot closer together in builds.

Positions To Save: Optimization option that lets you specify how many positions in time to save in memory. This should probably be at least Images To Display * Delay Between Images, or things might look weird.

Use Multicolors: Check this if you want each Afterimage to use a different color. If you do, use the Multicolors list to specify each image's color. The Multicolors list's size should be equal to Images To Display or things might break!

