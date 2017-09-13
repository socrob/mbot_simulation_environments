How to adapt furniture
======================

To calculate moments of inertia of all furniture-
(Using Windows & Solidworks)
Step 1

Open .dae file in MeshLab, verify & note approximate measurement of longest side of object, and units.

Steps 2

Export to .stl using MeshLab. Verify dimensions.

Step 3
Using Solidworks, click on File>Open> Select file extension as .stl and click on "Options".

In Options, choose "Import as Solid Body". Now open the .stl file.

Step 4 
Check dimensions and Axes (X,Y,Z) relative to actual orientation of object in the rockind213.world file.

Use as guidelines - actual mass of object & rough densities-
http://www.engineeringtoolbox.com/wood-density-d_40.html

Assuming uniform density of material of object, enter a density which calculates to the right total mass for the object.

Note down the inertia tensor (Ixx,ixy,ixz,iyx,iyy,iyz,izx,izy,izz) and center of mass.
Transform the tensor for the appropriate X-Y-Z directions to align with the rockind213.world.

Enter the mass, center of mass and inertia tensor in the <collision> tag & its attributes for the objects specified in the file rockind213.world, and remove the "fixed" setting for objects.
