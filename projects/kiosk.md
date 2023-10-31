# FabLab EDP Kiosk

###### tags: `projects` `kiosk` `cnc` `laser-cutting` `3d-printing` `solidworks` `rhino` `electronics` `raspberry-pi` `nodejs`


We built this kiosk to register projects and users at our FabLab, providing a project gallery and records of human and machine hours.  
The software and CAD files are available on GitHub: [github.com/fablabedp/fablabedp-kiosk](https://github.com/fablabedp/fablabedp-kiosk)  

![](images/kiosk/kiosk.jpg)  

![](images/kiosk/ui_project_list.png)  

Users can upload media, register hours, leave updates and feedback, and give a final project evaluation. It also includes a photobooth tool that lets you take photos with the kiosk and associate them with projects or leave them in the photobooth gallery.  Media on the kiosk can also be sent to users by email.

![](images/kiosk/ui_project_details.png)  

The kiosk hardware uses a Raspberry Pi 4 in a CNC machined PVC stand. The kiosk software is built mostly with with Node.js and runs in chromium's kiosk mode. A  Raspberry Pi Camera Module 3 is used for the photobooth.


---

We designed a version using the Raspberry Pi 7in touch display, but ended up using a standard 21in lcd monitor.  There is a removable shelf for mouse and keyboard, in the touchscreen version it is smaller and designed to be hung vertically when not in use.  

![](images/kiosk/kiosk_cad.jpg)  

The structural parts are machined from 15mm expanded PVC.

![](images/kiosk/CNC_parts.jpg)  

We used a v-cutter to miter the corners of the kiosk tower.

![](images/kiosk/vcut_chamfer.jpg)  

We assembled a test part to evaluate the miter cuts and slot fits. We experimented putting a 3mm fillet on the edges once assembled but decided to keep them sharp instead.

![](images/kiosk/test.jpg)  

The front and sides are screwed and glued together with an acrilic adhesive, and the rear panel is attached with machine screws and threaded inserts.

![](images/kiosk/assembly_parts.jpg)  
![](images/kiosk/assembly_glued.jpg)  

The Raspberry Pi is cooled with a 220V fan, and we added an on/off switch and fuse which are hidden under a printed cover on the rear panel.

![](images/kiosk/raspberrypi_assembly.jpg)  

![](images/kiosk/camera_assembly.jpg)  

The camera assembly has a removable rear panel that allows the camera to be rotated 180 degrees.

![](images/kiosk/camera.jpg)  

To attach the tower to the base we used brackets from some [leveling feet](https://www.amazon.es/IGNPION-Nivelador-patas-muebles-piezas/dp/B09XXQ6LMD/), and we put locking coaster wheels on the base.  We included a 4G router inside the tower for providing connectivity to the kiosk when taking it to external events.

![](images/kiosk/kiosk_back.jpg)  






