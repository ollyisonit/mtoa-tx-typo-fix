# MtoA TX Typo Fix

Fixes two typos in the `arnoldRenderer.xml` file that break batch rendering command line flags relating to TX files. Specifically, they prevent the batch render command line arguments from being correctly mapped to attributes in the Maya scene.

Note that this fix is a hack that involves messing with your program files and should be done with caution. I've contacted Autodesk and they said that this bug will eventually be patched, but for now we can fix it ourselves.

## The Fix

### ai:txamm Flag (Enables/Disables auto mipmap)
Change the line

``` xml
<attr n="ai:txamm" s="defaultArnoldRenderOptions.textureAutomp" t="boolean" h="Enable texture auto mipmap."/>
```

to

``` xml
<attr n="ai:txamm" s="defaultArnoldRenderOptions.autotx" t="boolean" h="Enable texture auto mipmap."/>
```

### ai:txett Flag (Uses/Does not use existing tiled textures)

Change the line

``` xml
<attr n="ai:txett" s="defaultArnoldRenderOptions.user_existing_tiled_textures" t="boolean" h="Use existing tiled textures."/>
```

to

``` xml
<attr n="ai:txett" s="defaultArnoldRenderOptions.use_existing_tiled_textures" t="boolean" h="Use existing tiled textures."/>
```

## Installing

Either replace your `arnoldRenderer.xml` with the one in this repository, or make the above edits to your `arnoldRenderer.xml` file. You can find `arnoldRenderer.xml` in your Arnold installation folder (for example, `C:\Program Files\Autodesk\Arnold\maya2023\arnoldRenderer.xml` on Windows).