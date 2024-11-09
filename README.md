# BCRYExporter
This is ported version of BCRYExporter for Cryengine 5 from https://github.com/AFCStudio/BCRYExporter for Blender 2.93+ <br>
This version is based on https://github.com/LeonidasWhite/BCRYExporter
 
<b>Installation:</b>
Copy `io_bcry_exporter` folder to blender_path\Scripts\Addons directory.

<b>Example:</b> C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons

<b>Documentation:</b> Contained in this repo

<b>NOTE: The following description is not up tp date</b>
<b>Known issues/limitation:</b>
1) Custom split normal doesn't support Sharp edges in skin node. <br> <b>Solution:</b> Add Edge split modifier before Armature modifier, set up and apply. The skin mesh will be rip in Sharp edges places.
2) There is no way to set active any collection, so be careful that current active collection be unhide and not disable. Otherwise you can expect Error that Object is Null. I put in some operators code which set Master collection(Scene Collection) active.
3) In some cases when you modify the armature as add bones through edit_bones.new() method or other way BCRYExporter will be export armature with broken bones hierarchy. I think that is Blender bug because I nothing changed in export code except fix errors with Bmesh convertation. <br> <b>Solution:</b> I added a button in Bone utilities: Rebuild-armature. It rebuild selected armature from zero and copy all bones parameters: name, matrix, roll, parent, some properties and custom properties then delete old bones. It don't copy bone constraints at the moment.<br> <b>IMPORTANT:</b> vertex groups renames too, but only if the object is a children of this armature. Do skin object a child of armature before use this button.
