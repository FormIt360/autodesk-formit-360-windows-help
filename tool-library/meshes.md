# Meshes

Starting in v17.0, FormIt offers a new type of geometry: Meshes. 

Meshes are lightweight representations of standard FormIt Objects, and are great for improving the performance of high-polygon geometry like furniture or 3D entourage like people, trees, cars, and signage. Meshes are also great for complex DWG geometry that might otherwise affect FormIt's performance. 

Objects can be converted to Meshes, and Meshes can be converted back to Objects without losing any data. Learn more about converting between types, and other benefits and limitations of Meshes below.

### Converting Objects to Meshes

Any combination of edges, faces, or solid bodies can be converted to Meshes. 

Simply select Objects, and either use shortcut OM \(Objects to Meshes\) or right-click and select Objects to Meshes in the Context Menu:

![](../.gitbook/assets/context-menu_object-to-mesh.PNG)

Once the objects have been converted to Meshes, you'll see a confirmation message at the top of the screen:

![](../.gitbook/assets/success_object-to-mesh.PNG)

**When converting Objects to Meshes:**

* Edges that were smoothed on the Objects will remain smoothed in the resulting Meshes.
* Material orientations on the Objects will remain unchanged in the resulting Meshes.
* A Mesh is created for every material applied. For example, if you convert a single cube painted 6 different colors, you'll get 6 different Meshes.
  * Converting back to an Object will re-seal the individual meshes back into a solid body.

**Converting Grouped geometry to Meshes:**

* Meshes become even more powerful when you can convert an entire Group and all of its nested Groups into Meshes.
* Groups and their nested contents can be converted to Groups by using a plugin:
  * Look for the Plugin Manager icon on the right side of the application:
    * ![](../.gitbook/assets/plugin-manager_icon.PNG) 
  * Find the "Mesh + Unmesh All" plugin, and click the checkbox to install it:
    * ![](../.gitbook/assets/plugin-manager_mesh-unmesh-all.PNG) 
  * The Mesh + Unmesh All plugin will load. Simply select a Group containing Objects you want to convert to Meshes, and click Mesh All.
    * ![](../.gitbook/assets/mesh-unmesh-all-plugin.PNG) 
  * When converting nested Objects or Meshes with this Plugin, you'll see an update message at the top of the screen telling you how many Groups and instances of Groups were affected by the operation. 

### Interacting With Meshes

Because of their lightweight nature, Meshes have certain limitations and behaviors:

* You won't be able to edit the individual faces, edges, or vertices of a Mesh.
  * However, you can repaint Meshes and move individual Meshes created as a result of different materials applied to faces \(see above\).
* Snapping to Meshes is limited to the "faces" that comprise the mesh.
  * You won't be able to snap to edges or vertices of a Mesh
  * However, DWG files converted to Meshes \(a different type of mesh known as a Linemesh\) will retain the ability to snap to edges and vertices.
* Meshes cannot have Levels applied to them.
* Meshes will not report watertight or backface issues. Convert them back to Objects to see whether they are watertight or not.

### Converting Meshes Back to Objects

Simply select Meshes, and either use shortcut MO \(Meshes to Objects\) or right-click and select Meshes to Objects in the Context Menu:
