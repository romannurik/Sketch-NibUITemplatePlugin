[![No Maintenance Intended](http://unmaintained.tech/badge.svg)](http://unmaintained.tech/)

# Sketch Nib UI Template Plugin

This repository contains a template/example Sketch plugin whose UI is built in Interface Builder (and output
as a .nib file, hence the name). The .nib is then loaded in through CocoaScript using some pretty brittle
hackery, so beware.

# Screenshots

<img src="https://raw.githubusercontent.com/romannurik/Sketch-NibUITemplatePlugin/master/art/screenshot_interface_builder.png" width="500" alt="Interface builder">
<img src="https://raw.githubusercontent.com/romannurik/Sketch-NibUITemplatePlugin/master/art/screenshot_plugin_running.png" width="287" alt="Running plugin">

## Instructions

 1. Clone the repository.
 2. Open up `SketchNibUITemplate.xcodeproj` in XCode and in Interface Builder, modify `SketchNibUITemplate.xib` to the UI you want for your plugin.
 3. Add some view property definitions in [`DummyNibOwner.m`](https://github.com/romannurik/Sketch-NibUITemplatePlugin/blob/master/SketchNibUITemplateProject/DummyNibOwner.m) so you could reference views in your UI from CocoaScript.
 4. In Interface Builder, open up the **File's Owner** object and in the **Connections inspector**, connect the outlet for the properties you just defined to the actual views in the UI you made.
 5. In Interface Builder, click **File > Export** and change the File Format to **Interface Builder Cocoa NIB**.
 6. Save the .nib as `your.sketchplugin/Contents/Resources/UIBundle/Contents/Resources/MyNibUI.nib`.
 7. Update your [CocoaScript file](https://github.com/romannurik/Sketch-NibUITemplatePlugin/blob/master/SketchNibUITemplatePlugin.sketchplugin/Contents/Sketch/example_script.cocoascript) to load in the extra view properties (such as `exampleButton`).

Also don't forget to update the [plugin manifest](https://github.com/romannurik/Sketch-NibUITemplatePlugin/blob/master/SketchNibUITemplatePlugin.sketchplugin/Contents/Sketch/manifest.json) to give your plugin a unique name, ID, etc.
