--- 
layout: post
title: Minecraft, Blender, and mcobj
wordpress_id: "301"
wordpress_url: http://geeklob.wordpress.com/?p=301
categories: Uncategorized
---
If you want to make images of your Minecraft world like <a href="http://i.imgur.com/c3Nsv.jpg">this</a>, <a href="http://i.imgur.com/hUxFo.jpg">this</a>, <a href="http://www.flickr.com/photos/macs4all/sets/72157626566696220/">these</a>, or <a href="http://quag.imgur.com/minecraft__blender">these</a>, you have come to the right place.

This tutorial is aimed at *nix  (linux, mac, etc.) systems workflows, mainly because those are the systems I have. I will include windows instructions, but they aren't tested, or are tested less than the *nix instructions. Luckily, the differences shouldn't be too great.

<!--more-->
# Requirements
<ul>
	<li>A good computer. You need a computer capable of playing video games which are more demanding than Minecraft, and you basically require an actual graphics card.</li>
	<li>A modern operating system. I'm uncertain as to the precise requirements, but any modern linux distro, Mac OS X Tiger, and probably a windows version as old as XP will work just fine.</li>
	<li>Minecraft. For targeting the render. A mapping program would also work.</li>
	<li>InvGrid (or similar)</li>
	<li>Blender, at least version 2.5 or greater.</li>
	<li>mcobj, and mcobj-gui. I'll cover installation in the tutorial.</li>
</ul>
# Overview
Workflow:
<ol>
	<li>Find target.</li>
	<li>Convert world to .obj with mcobj and mcobj-gui</li>
	<li>Import .obj into Blender.</li>
	<li>Adjust render in Blender.</li>
	<li>Render with Blender and export.</li>
</ol>
# Targeting
If you have an absolute beast of a computer, and a fairly small world, you can skip this section.

Due to hardware limitations (my computer can't handle more than a few million vertices in Blender for editing), we frequently can't convert the entire map to .obj. When you convert a world to .obj, the size increases. I have not had time to study carefully this relationship, but I know that if your world is about 100 megs, the resulting .obj file will be 2.5 gigs, and unless you have  a beast of a machine, you can't import .obj files that large into Blender (at least, I can't.)

Therefor, we must take advantage of mcobj's ability to constrict the portions of the map it uses. First, you need to find, either in Minecraft using F3, or using another mapping program, the coordinates of your target. You need the x and the z coordinates. Note that these are block coordinates. Next, you need to find out whether your target will be contained by a 40 chunk sized square around your target. You can basically assume that 40 will work, but for larger creations, you may need to increase this number. You have now determined everything you need to know to target and restrict your render.

Note that if you want to render the area around your spawn, you may need something like InvGrid to determine the coordinates, because minecraft does not spawn you at 0,0.
# Installing mcobj and mcobj-gui
The linchpin of this entire operation is mcobj and, to a lesser extent, mcobj-gui. Step one is to make sure you can extract 7zip files.

On Ubuntu (and perhaps Debian)

`sudo apt-get install p7zip`

For Windows: Download and install from <a href="http://www.7-zip.org/">here</a>.

Mac: While I haven't tested, <a href="http://www.macupdate.com/app/mac/19139/ez7z">this</a> seems to claim to work.

Next, download mcobj from <a href="https://github.com/quag/mcobj">here</a>. Unzip. You should now have a small executable called mcobj. Remember where you unzipped this, it will be important.

Next, download mcobj-gui from <a href="http://code.google.com/p/mcobj-gui/">here</a>. It should also produce an executable. Remember where you unzip this executable as well.
# Converting the world
Now you have all the tools you need (assuming you already have Blender installed. See blender.org for installation instructions.)

Now, launch mcobj-gui. You will see a window pop up with lots of different controls. On the left side, you can see the file selector for the save file to process, the output .obj file, and the location of mcobj. On the other side, you can see other, mcobj specific controls, and on the bottom left, there are some options.

Step 1 is to let mcobj-gui know where mcobj is. Find, in this window, the file selector for "mcobj location", which at this point should be "(unknown)", click the select button, and navigate to the mcobj executable. Next, use the top file selector (labeled "Save file to process"), click select, and navigate to the save file you want to render. Search around and see if you can find the save location for your platform. On linux, it's ~/.minecraft/saves, and on mac is in ~/Library/Application Support/minecraft/saves, and in Windows, it has something to do with %AppData%. Google will be enlightening at this juncture. Finally, you will want to tell mcobj-gui where to save the .obj file. They suggest a location, but you may want to change that. Remember that it should end it .obj, and that mcobj will produce 2 files, a .obj and a .mtl file, and they need to be kept together.

Next, you will want to take the block coordinates from the targeting section, divide by 16 (as instructed by mcobj-gui (this is because Minecraft's F3 location finder works in block coordinates, while mcobj and mcobj-gui works in chunk coordinates)), and set the "Center of Chunk" fields to those numbers. Next, set size of chunk to 40, though if you need some other number for this flag, use it here. Determining size of chunk is beyond the scope of this tutorial. You also need to consider whether or not you need the blocks below sea level to be in this render. If you are render a surface creation (like a tower, city, etc.) that isn't below sea level, you can happily set "Omit blocks below" to 50. Note that I use 50 because if you use 63, as mcobj-gui suggests, if you have any water at sea level, you won't get to see the bottom of that lake, or it will get cut off mid lake, and it will look strange. If you are making a render of a giant pit, or something underground, you can't set this option.

Take a quick look over all your options, and make sure you have them all set correctly. Then click process. Watch the progress bar fill, or do something else, because this can take a while. You should try to remember where you saved the .obj file.<strong> If you need to move the .obj file, make sure you move the .mtl along with the .obj file.</strong>
# Working in Blender
At this point, proficiency in Blender becomes important, because if you need anything strange in mcobj, the strangeness will be carried over into Blender (to a certain extent.)

A full tutorial in Blender is beyond the scope of this tutorial, though I heartily suggest <a href="http://en.wikibooks.org/wiki/Blender_3D:_Noob_to_Pro">Blender: Noob to Pro</a> for learning at least the basics of Blender. They will come in handy later in this tutorial.

Launch Blender. Once Blender has launched, click to clear the pop up of a Chameleon (or similar) and move your mouse into the 3D view (the one with the cube floating in space.) Hit x, don't move your mouse, and click. This will delete the cube. We don't need it. Hit 7 on your key pad to move to an overhead view. Hit the space bar, and type "import obj", then hit enter. A file selection box should replace the 3D view. Find the .obj file mcobj produced, select it, and hit import. This will take a while (roughly proportional to the size of the chunk of the world you converted.)

At this point we face a problem. If you targeted an area of your world more than about 50 chunks away from 0,0, you won't be able to see anything. Zoom out, and you should quickly be able to see your terrain. If your terrain isn't in the center of the Blender screen, hover your house over the center of the terrain, hit g, then move your mouse to the center of the 3D screen, and click. The terrain should move with your mouse.

Next, hit 0 on your numpad. This will move your view to the camera view. Camera manipulation is complex, but if you select the camera, and hit g, you can roughly pan around. However, getting a good angle will require more manipulation than that, and that's where <a href="http://en.wikibooks.org/wiki/Blender_3D:_Noob_to_Pro">Blender: Noob to Pro</a> comes in handy.

Next, look to the right side bar. You should see an incredibly complex and obtuse panel of settings. Don't try to understand these, just observe the row of icons running along the almost top, starting with a camera. You should see a little blue sphere. Click it, then look down to the panel and find "Ambient Occlusion", and click the checkbox next to it. Then click on the littler camera in the row of icons. Click the button that says "Image", or hit F12 (assuming nothing else on your computer is using F12) to render. The 3d view should be replaced with a grey grid that, after a while, will turn black, then start filling with the render. When it is done, look over the image, then hit ESC. If you weren't happy with the image, adjust it, then render again. Repeat until you are happy with your render.

When you are happy with your render, return to the 3D view, and look over to the panel with the row of icons. Ensure the camera is selected. Look down until you see a little arrow followed by "Dimensions." Below that, you should see 2 fields below "Resolution". One should be labeled X, and the other Y, and in my case, they are set to x = 1920, while y = 1080. You want your image to look really good, while maintaining the same aspect ratio. Click on 1920, replace it with 7111, click on 1080, replace it with 4000. Render again. This will take longer. Finally, you should have a very large render of your world. When it is finished rendering, hit F3. Another file selection box should replace the render, but instead of finding your .obj file, you are instead saving the render. Navigate to your desired location, type in a name (make sure you keep the .png at the end of it) and hit Save.

You have successfully render and saved out your mcobj render. Congratulations.
