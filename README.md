# 3D-format-study

## OBJ Format:
**Features:**
- The biggest strength of the OBJ file format (and its sister MAT material definition file format) is that it is text-based and very simple to understand.
- Simple and widely supported 3D file format that describes objects rather than scenes
- Can be used for simple geometry interchange
- Supports basic 3D model geometry and texture mapping

**Limitations:**
- Can only contain a single model, rather than an entire scene
- Unable to represent complex 3D models and lacks support for vertex colors or custom attributes
- No support for animations, PBR materials, or scene graph data structure
- Limited support for texture maps and UV mapping
- While OBJ files can be loaded in a web browser, it's a very slow experience. 
- Text-based formats are slower to process compared to binary file formats.

## glTF Format:
**Compatibility:**
- Gaining popularity as a modern and efficient format for real-time and web-based 3D graphics

**Features:**
- Modern 3D file format designed for efficient transmission and loading of 3D scenes and models
- JSON is easy to read, write and has parsers available in most languages.
- glTF can be read more than 10x faster than a file format that stored the bulk 3D geometry in human-readable text (like OBJ)
- glTF stores mesh data in a unified topology, allowing for direct GPU memory rendering without intermediate processing required for OBJ mesh data.
- Supports physically-based rendering (PBR) for realistic lighting and shading of 3D models
- Supports scene graph data structure for efficient representation of complex hierarchies and scene structures
- Supports animation, morph targets, instancing, and more advanced materials
- Stores binary data (such as vertex and index data) in a separate .bin file for faster loading times and smaller file sizes 
- Supports separate textures in formats such as JPEG or PNG
- Designed for real-time and web-based 3D graphics, such as gaming, virtual and augmented reality, and architectural visualization
- The glTF format is better than FBX if you want to transmit your 3D scene data efficiently over the internet for viewing in a remote application, such as for the purposes of augmented reality.

**Limitations:**
- Unable to represent some complex 3D models. glTF is designed for representing polygonal meshes and does not have native support for NURBS or CAD data.
- Limited support for custom attributes and vertex colors
- glTF supports basic rigging and animation but does not support some of the more advanced features like constraints and deformers found in other 3D file formats such as FBX.
- May not be suitable for larger and more complex scenes due to limitations in memory management
- To load faster, it does not allow for differing topology for positions, UV, and normal data like FBX, so later editing is not possible.

## FBX Format:
**Features:**
- Proprietary 3D file format developed by Autodesk
- The FBX SDK simplifies reading/writing FBX files, enabling transfer of 3D data between tools
- Supports a wide range of features, including geometry, materials, hierarchy, lighting, animation, deformers, and constraints
- Can be used for interchanging complex 3D models between various 3D software
- Supports real-time rendering and previewing of scenes
- FBX, as an older format, also supports data that isn’t widely used today, such as NURBS surfaces and curves
- At a high level, the FBX file format is better than glTF if you're transferring your data to a game engine like Unity or Unreal Engine or between 3D tools.

**Limitations:**
- Proprietary status, which may result in support issues compared to open formats like glTF and USD
- If you want to load an FBX on a system that is not officially supported by the FBX SDK (such as in a web browser or an open-source application), you cannot do so.
- The FBX format has dated features and is proprietary, requiring a large proprietary C++ SDK for loading. Due to these limitations, FBX cannot be directly loaded in a web browser.
- Complexity, which may make it less suitable for simpler 3D models or workflows that do not require such advanced features
- Limited support for customization and scripting in comparison to other formats

## USD Format:
**Compatibility:**
- The animation, FX, layout, and lighting departments collaborate to create the scene. At each step, creators make edits, produce options, and vote with “opinions.” The director decides on what to use.
- USD stands for Universal Scene Description, USDZ is a zip-compressed version and USDA is a human-readable text format.
- USDZ is adopted by Apple for real-time 3D content packaging in iOS applications and web-based Quick look AR experiences.
- Mainly used for large VFX/Animation studios with complex pipelines

**Features:**
- Used in collaborative framework for people working on 3D scenes
- Modern, open-source 3D file format developed by Pixar Animation Studios
- The USD file format, because it utilizes an efficient binary encoding, is fast to write and read. 
- Supports all 3D concepts such as geometry, materials, hierarchy, animation, physics, and simulation data
- Supports layering of scenes, opinions, variants, and non-destructive editing
- Designed for large VFX/Animation studios with complex pipelines
- USD allows for complete scene compositions to be stored and shared, whereas glTF is all about individual 3D assets

**Limitations:**
- Complexity, which may make it less suitable for simpler 3D models or workflows that do not require such advanced features
- USD is designed for rich visuals over the various space-saving techniques that other 3D formats, such as glTF, employ.
- USDZ doesn't have legacy features like FBX's support for NURBS surfaces.
- USDZ does not employ 3D geometry-specific compression algorithms; therefore, it loses out on the compression ratios that glTF can achieve with DRACO compression. 
- USDZ file uses a zip file container to bring together all of its component files into one package, it does not allow currently for the zip compression feature to actually be enabled to make the file size smaller.
- USD lacks Draco geometry compression, which glTF supports.

References:
1. [Sketchfab - glTF, GLB, and USDZ](https://help.sketchfab.com/hc/en-us/articles/360046421631-glTF-GLB-and-USDZ)
2. [Marxent Labs - USD Files](https://www.marxentlabs.com/usd-files/)
3. [OpenUSD - USD FAQ](https://openusd.org/release/usdfaq.html)
4. [KhronosGroup - glTF GitHub Repository](https://github.com/KhronosGroup/glTF)
5. [Ben Houston's on 3D File Formats - Threekit - When Should You Use FBX 3D File Format?](https://www.threekit.com/blog/when-should-you-use-fbx-3d-file-format)

