FRAPPA setup
============

.. figure:: /images/thumbnails/frappa-calibration.png
   :figwidth: 25%
   :width: 100%
   :align: right

   Resulting difference image stack of automated calibration routine.

.. contents:: Contents


Uniform fluorescent slide
-------------------------

1. Focus on the Ethidium Bromide calibration slide with the eyepieces
   using transmitted light.  The liquid layer is thin and can require
   refocusing every few minutes.

2. Use a camera exposure of 200-500ms for imaging.  As with most image
   processing calibration algorithms, a fair amount of signal is
   necessary for an accurate image registration.


First time hardware setup
-------------------------

.. warning::

   These steps are only necessary when mechanically aligning the
   FRAPPA galvo system with it detached from the microscope.

1. Select the "Illumination setting (during pulse)" and "Illumination
   setting (during imaging)" in the Configuration tab.
   
2. Adjust the "Rest Position" angle in the Setup tab to center
   illumination on the C-mount target on the FRAPPA excitation
   aperture.

.. image:: /images/calibration/frappa01_setup.png
   
3. Click the "Save" button when you are happy with the bypass
   position.
   
4. In the Configuration tab, set the "Dwell time [us]" to 10,000
   (without the comma) for an EMCCD, or 100,000 for other cameras.
   
5. Click "Pulse" back in the Setup tab and adjust the offsets (by 0.1
   increments) to center the laser spot on the center of the image.
   
6. Cycle MetaMorph so that these setup values are written into the
   ``mmproc.cfg`` file, just in case the software crashes.  The more
   convenient way of using File > (holding Shift key) + Exit
   unfortunately does not save FRAPPA settings.


Steps to calibrate
------------------

.. note::

   On multi-user MetaMorph systems, it is recommended to create a
   special user to use "Targeted Illumination" hardware, like the
   FRAPPA, Mosaic and Micropoint.

   The "Targeted Illumination" calibration settings are stored in each
   user's ``mmproc.cfg``, and there are no "Backup..." or "Restore..."
   buttons (or journal functions) to make it possible to to keep
   calibrations up-to-date for every user.


1. A safe value for  "Range for calibration point" for EMCCDs is
   20% to 30%
   
2. Enable "Display images during calibration".  This allows you to see
   the difference images as the software is doing the automated
   calibration, providing useful diagnostic information.
   
3. There should never be any need to use "Manually click on
   calibration points" with the FRAPPA since we have good control over
   the laser settings.
   
4. Enable autoscaling in the Acquire window's Display tab.

.. image:: /images/calibration/frappa02_calibration.png
   
5. Select the "Mag:" setting for the current objective + camera
   combination in use.

.. image:: /images/calibration/frappa03_mag.png

.. note::

   MetaMorph ties together the name of the Magnification setting to
   the Calibration setting; i.e. the Calibration name is the same as
   the Magnification setting.  When using multiple cameras with the
   Targeted Illumination device (such as a multi-camera Confocal or
   back-port FRAPPA system), create a Magnification setting for each
   camera like "100x EMCCD" and "100x sCMOS"
  
6. Finally, click "Create Setting...".  During calibration you will
   see each point pulsed in a 3x3 grid.

.. image:: /images/calibration/frappa04_during_calibration.png

7. The new calibration setting appears in the "Coordinate system
   setting" dropdown list, if successful. 

8. Repeat steps 5 and 6 for all objectives with sufficient NA.

9. **Important**: Change the "Dwell time [us]" back to 100, otherwise
   trying to FRAP 2D regions will take several minutes instead of the
   low order of seconds!

10. Optionally, you can draw a small region of interest and click
    "Pulse" to test the calibration.  There are 2 different "Pulse"
    buttons: one under the Configuration tab and one under the
    Location tab.  Use the "Pulse" button in the Location tab.


Customizing the interface
--------------------------

Create 
