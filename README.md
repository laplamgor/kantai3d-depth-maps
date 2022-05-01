[⬅️ back to top repo](https://github.com/laplamgor/kantai3d)

# Kantai3D Custom Depth Maps
This repository stores all the manually painted depth map files used in Kantai3D Mod.

Feel free to download and contribute.

Does not contain any original game content of Kancolle.

Does not include the AI generated depth maps which are also used by Kantai3D but have rougher quality and are difficult to edit.

# Depth Map format

All depth maps are in PNG format with RGB channel and 24-bit color depth. 

The depth map file does not contain any original image data.

## RED channel (0-255)
Red channel stores the the depth values. 

Higher value = closer to camera. values also have a linear scale.

g=127~128 is near the pivot point. Pixels there will have no parallex effect when tilting in Kantai3D.



## GREEN channel (0-255)
Green channel stores the the mask (layering) data. 

The mask data has no impact to in-game effects, but are useful when editing depth maps.

Kantai3D supports 256 masks (#0 to #255). Every pixel must belongs to one and only one mask.


## BLUE channel (0-255)
Blue channel stores the the jiggle strength data. 

It actually changes both following phyiscal attributes:
1. Damping force: affect how fast a motion decays to stationary; lower = jiggle for longer
2. Springiness: affect how strong a pull back force is;

b=0 will make a pixel completely stationary. 
High blue values will make these force smaller. Since `F=ma` it is similar to being a heavier object.

Avoid using b=1 to 5 which is currently buggy in Kantai3D.

p.s. Blue values are only being sampled on a 10px * 10px grid vertices in Kantai3D. e.g. (0,0) (0,10) (10,0) (10,10) ....



# Downloading via jsdelivr CDN

Kantai3D Mod downloads custom depth maps from this repo via jsdelivr CDN.

The URL of a depth map will be like:

https://cdn.jsdelivr.net/gh/laplamgor/kantai3d-depth-maps@master/source/0412/0412_7506_xjsgvmgfleuu_v45.png




# Progress Updates

You can find all currently supported ship name list here: 

https://github.com/users/laplamgor/projects/3/views/1

Currently Kantai3D does not have any custom depth map for medium damaged CG.
