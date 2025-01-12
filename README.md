# Crosshair Cursor

### In this tutorial, we will be assigning a crosshair to the cursor

> [!IMPORTANT]
> In this tutorial, you will need any version of Unity and VisualStudio released within the last 5 years
> 
> This tutorial is made for a 3D Project
> 
> For this tutorial, you will need to download a .png of the crosshair you wish to use. Ensure that it has no background for best results.

> [!NOTE]
> This tutorial shares the same project as my other tutorial, **Camera Waypoints**. You don't need to have viewed it to follow this tutorial, but it's worth keeping in mind if you don't recognise objects in the Heirarchy.

### Part A. Creating the UI

1. Open `File Explorer` on your computer, locate your crosshair png and drag it into assets.

<img width="551" alt="image" src="https://github.com/user-attachments/assets/bf4270e0-ba94-4d1a-a3ad-048f188dcb88" />

2. In order to add UI, we first need a Canvas. In `Heirarchy`, right click the `Main Camera`  -> `UI` -> `Canvas`.

3. Under `Inspector`, you should see `Render Mode` is set to 'Screen Space - Overlay'. Change it to 'Screen Space - Camera' and drag your Main Camera to the `Render Camera` tab.

<img width="398" alt="image" src="https://github.com/user-attachments/assets/e29265c1-daaf-4284-99da-232dc7eea34c" />

4. Right click `Canvas` -> `UI` -> `Raw Image`. This will display a white box in the middle of the canvas. Hit F2 to rename it to 'Crosshair'

5. Drag and drop your image into the `Texture` tab and click the button below that says `Set Native Size`. You can scale the image above using `Rect Transform`, but ensure the link icon next to `Scale` is enabled.

<img width="961" alt="image" src="https://github.com/user-attachments/assets/32a99383-fad0-4aec-ace3-027b6aff61d5" />


### Part B. Creating the code to link the crosshair to the cursor

1. Right Click in the `Assets` window, -> `Create` -> `C# Script` and name the script 'FollowMouse'. Double click to open in VisualStudio.

2. Within the `public class` brackets (above `void Start()`), we're going to add a 3D position and a speed variable.

   `Vector3 pos;`
   
   `public float speed = 100f;`
   > public simply means you can edit the number from unity

3. Under `void Update()`, type in the following;

   `pos = Input.mousePosition;`
   > Position is the mouse position

   `pos.z = speed;`
   > Z position is equal to speed (though I'm not sure how or why that's gonna work on a 2D UI element-)

   `transform.position = Camera.main.ScreenToWorldPoint(pos);`
   > Also lacking knowledge on why this works

Save your script and return to Unity.

4. Drag and drop your `FollowMouse` script onto `Crosshair`.

### Hit Play, and now your crosshair _*should_ be following your mouse movements.
