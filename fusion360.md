# Fusion 360

**[Wiki Home](https://hackmd.io/@fablabedp/home)**

###### tags: `CAD` `fusion360`

## Moving files between projects or teams

1. Open the file in Fusion.  If moving multiple linked files, you only need to open the file which uses the other linked files.
2. Save as Fusion 360 Archive File (\*.f3d): `File > Export`
3. If moving between teams, close open files and change the workspace to the team you want to import the file into.
4. Open the archive file: `File > Open > Open from my computer`
5. Save the file to the new location: `File > Save`

## "Missing qt5core.dll" error

Run the "Repair Fusion 360" tool from the Fusion 360 Service Utility:  
`System Settings > Apps and Features > Autodesk Fusion 360 > Modify`  
[Overview of Fusion 360 Service Utility](https://knowledge.autodesk.com/support/fusion-360/troubleshooting/caas/sfdcarticles/sfdcarticles/Overview-of-Fusion-360-Safe-Mode.html)  
[How to launch the Fusion 360 Service Utility](https://knowledge.autodesk.com/support/fusion-360/troubleshooting/caas/sfdcarticles/sfdcarticles/How-to-launch-the-Fusion-360-Service-Utility.html)  

# PocketNC CAM in Fusion

B-table offset sketch as WCS Origin: “Center of Rotation” programming  
	- real-world setup must match your 3D model setup closely for the machine to cut the stock in the right place  

WCS Origin point that is relative to the stock or part: RWO "Rotated Work Offsets"  
	- works better in some situations, but is only suited to 3+2 machining toolpaths.  