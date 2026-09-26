## Description

Efficient and flexible 5-tile dual-grid autotiling solution written in GDScript, with full support for randomization. 

Adds the AutoMapLayer class, which is then extended for each TileSet layout, letting the user hardcode its logic for pairing tile neighbor configurations with tile atlas coordinates.

Also adds the ShuffleMapLayer class, which has more basic randomizing features for background tilesets.

## Getting Started

* Extract the "addons" and "script_templates" folders into your project's root directory.
* In the Scene Tree, create an AutoMapLayer node.
* With your new node selected, click the "Extend Script" button.
* Set the template to "New AutoMap".
* Edit the script's get_tile() function to return the appropriate atlas coordinates + transform byte for each tile.
    For examples, check out addons\5tile\5tile_demo.tscn. Feel free to delete this scene and the `demo` folder.
* In the Scene Tree, create a basic TileMapLayer node. It should not share heirarchy with the AutoMapLayer.
* Give this TileMapLayer a basic, one-tile tileset. For 16x16, you can use addons\5tile\dot_16.png.
* Set the 'layout' parameter of your AutoMapLayer to this new TileMapLayer.
* Paint tiles onto the 'layout' TileMapLayer.
* Press the 'update' tool button in the AutoMapLayer's properties.
* Viola!

## Live Drawing

In Editor:
* Select the AutoMap you'd like to draw with.
* In the "In-Editor Drawing" section, modify your "Draw"/"Erase"/"Disable" keyboard inputs.
* Enable the Draw Mode checkbox. While enabled, your "Draw"/"Erase" keyboard inputs will perform those operations at your mouse pointer location. The "Disable" input will toggle the checkbox off.
* You can deselect the AutoMap and keep draw mode on. This allows you to work without the "focus" effect that comes from selecting a TileMapLayer.
* Multiple AutoMaps can have Draw Mode enabled at the same time. Set up your layers with different "Draw"/"Erase" keyboard inputs for an efficient workflow!

In Game:
* The AutoMap demo scene (res://addons/5tile/5tile_demo.tscn), which shows off example AutoMap configurations, now has in-game drawing set up.
* This requires "click_left" and "click_right" inputs in the Input Map, used for drawing and erasing respectively.
* Cycle between layers with "ui_accept" (e.g. SpaceBar)
* Programatically tallies up the AutoMaps at runtime, meaning you can add your own AutoMaps and seamlessly integrate them w/this system if they follow the existing format.

## License

This project is licensed under the MIT License - see the LICENSE file for details

## Acknowledgments

Built on the backs of these YouTube videos:
* [jess::codes - _Draw fewer tiles - by using a Dual-Grid system!_](https://www.youtube.com/watch?v=jEWFSv3ivTg)
* [Coding With Russ - _How To Rotate Tiles with Code in Godot_](https://www.youtube.com/watch?v=S-By5EvhIy8)