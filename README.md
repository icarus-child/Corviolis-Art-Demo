# Corviolis Art Demo
### The Challenge
The game is 2d from a technical perspective, but our team wasn't sure how we wanted to approach the art. After some consideration we decided we wanted to have a pixel art aestetic for both the approachability that it provides, and the cozy, nostalgic feel pixel art provides, which would fit the retro setting of the game. However, we also wanted to be able to experiment with the unique interactive and dynamic lighting working in 3d provides, this dichotomy created a unique issue.
### The Process
Since I knew the lighting would have to be 3d simulated no matter how the process turned out, I started by working in [blender](https://www.blender.org/).  
The final game will be made in [godot](https://godotengine.org/), which has great compatibility with blender, so it was a safe starting point.  
I started by attempting to place a raw 2d image into a 3d world and seeing how it looked.  
<img src="https://github.com/icarus-child/Corviolis-Art-Demo/blob/main/testscene1.png?raw=true" alt="testscene1.png" width="600"/>  
While the rather extreme lighting doesn't seem too jarring with the character, the realistic reflections are quite obnoxoius, and don't fit with the visual style at all.  
Also within the scene, I experimented with 3d lighting on smaller objects, and I 3d modelled a box shape based off the radio texture, and then baked it onto the plane holding the radio texture, as seen below.
| Lit from the left | Lit from the right |
| --- | --- |
| ![normalmapleft.png](https://cdn.discordapp.com/attachments/913544690593320970/939050593450864640/unknown.png) | ![normalmapright.png](https://cdn.discordapp.com/attachments/913544690593320970/939050844203126814/unknown.png) |

The garbage bag on the right is an earlier attempt at using a hand painted displacement map to make more organic shapes, but using a displacement map, while being easier to work with than a normal map, inherently held issues, and working without being constrained to the pixel grid had undesireable results, so this was discarded for a better method.  
I did some looking around for methods of hand painting normal maps, and I found [this](https://www.youtube.com/watch?v=gUkY8ZoRfuQ) youtube video on the topic by [ThePassiveAggressor](https://www.youtube.com/user/ThePassiveAggressor), which came with an invaluable reference image that could be used to sample colours for different light angles when painting the normal map.  
Armed with this resource, I began on a more complete test environment to see how the lighting looked in action.  
<img src="https://github.com/icarus-child/Corviolis-Art-Demo/blob/main/dock%20scene.png?raw=true" alt="dockscene.png" width="600"/>   
The scene includes 3 light points, some slight fog, and a bit of global illumination. The focus of the scene was the rocks, as they are a collection of fairly complex organic shapes that without this method would have a terrible reception to dynamic lighting.
| Lit from the left | Lit from the right |
| --- | --- |
| ![rocksleft.png](https://cdn.discordapp.com/attachments/913544690593320970/961616584592478298/unknown.png) | ![rocksright.png](https://cdn.discordapp.com/attachments/913544690593320970/961616496256229376/unknown.png) |  

While I could benefit from building a proper specular map for the surface, the rocks perform surprisingly well, I will continue to move in this direction in future testing.  
### The Conclusion
Hand painting the pixel maps, while somewhat time consuming, yields the best result by far. In the future I'd like to experiment with ways to lock procedurally generated textures to the pixel grid, but I will be continuing to use this method in my development.
