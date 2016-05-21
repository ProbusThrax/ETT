YongeTech Tech Trees Plugin (recompiled for 1.1)
version: 1.3
author: yongedevil  
============================


======================================
Contents
1.0 Description
2.0 Installation
  2.1 Know Issues
3.0 Creating a Tech Tree
  3.1 TechTree ConfigNode
  3.2 Custom Icons
4.0 Licence
--------------------------------------


================
1.0 Description:
----------------
By itself this mod doesn’t change the technology tree in Kerbal Space Program.  Instead, it adds support for other mods to do so more easily.
  - Allows part unlocks to be listed in the TechTree ConfigNode rather than having to edit every Part ConfigNode.
  - Adds support for using custom textures to create icons for the tech tree.
  - Adds a tree selection window to let the player select a tree for each new game.


=================
2.0 Installation:
-----------------
Copy the contents of GameData into the Kerbal GameData folder.

  2.1 Known Issues:
  -----------------
  This mod tracks parts by their name field.  This means if two parts have the same name, only the first will be editied.

  Both this mod and ModuleManager (on version 2.6.5 as of this writing) attempt to edit the tech tree of the current game.  This mod's changes should have priority.

  If you would like to disable the option to select a tech tree and the conflict with ModuleManager change the "allowTreeSelection" field in PluginData/YongeTech_TechTreesExpansion/config.xml from '1' to '0'.  This will keep support for the TechTree ConfigNode additions and custom icon support, but remove the option to select a tech tree.
  



=========================
3.0 Creating a Tech Tree:
-------------------------
The mod adds new support to the TechTree ConfigNode and will create icons for use in a tech tree from custom textures.

  3.1 TechTree ConfigNode:
  ------------------------
  The mod adds support for new fields and a new subnode in the TechTree ConfigNode.  Shown below is a sample TechTree node showing the new fields.

TechTree
{
  title = Sample TechTree
  description = An incomplete TechTree showing the basic setup
  unlockAllStartParts = True

  RDNode
  {
    ...
    
    Unlocks
    {
      part = solidBooster_sm
      part = probeStackAdapter
      part = standardNoseCone
      part = sensorThermometer
      part = basicFin
    }
  }

  ...

}


    3.1.1 TechTree Node Fields:
    title: The name of the tree.  Displayed in the tech tree selection window when starting a new game. (approximately a 45 character limit)

    description: Single paragraph description of the tree for the player.  Displayed in the tech tree selection window when starting a new game. (approximately a 400 character limit)

    unlockAllStartParts: If True the mod will automatically unlock all parts in the starting tech node(s), which are any tech nodes with a cost of 0.  This is only relevant if No Entry Purchase Required on Research is disabled in difficulty settings.

    3.1.2 Unlocks Node:
    The Unlocks Node is a new subnode for the RDNode in TechTree.  The Unlocks node has a list of "part" fields containing the names of all the parts unlocked by the RDNode.  The mod will read this data and handle editing the TechRequired on all the parts.


  3.2 Custom Icons:
  -----------------
  The mod also adds support for custom icons.  All icons should be placed in a directory named "RDSimpleIcons".  .png, .tga, and .dds formats are supported.  The mod will create a custom icon with the same name as the file, without the extension.

  .../RDSimpleIcons/customIcon_tech.png will become "icon = customIcon_tech"


============
4.0 Licence:
------------
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.