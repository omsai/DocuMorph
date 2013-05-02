Streaming with FRAPPA (using Live Replay)
=========================================

.. figure:: /images/thumbnails/frappa-live-replay.png
   :figwidth: 25%
   :width: 100%
   :align: right

   Resulting time stack using "Live Replay" tab in the "Acquire"
   window.  There is fast diffusion around thin rectangle bleach
   region.

Introduction
************

Don't use Multidimensional Acqusition, except for Z
---------------------------------------------------

Multidimensional Acquisition is often not suitable for FRAPPA
streaming experiments, because MDA does not allow running journals
(and thus using the FRAPPA) during a stream.  MDA only allows journals
to be run at the beginning or end.

If pre-bleach images are required with minimum delay between FRAP, we
can instead accomplish this type of experiment using the Live Replay.

.. note::

   MetaMorph 7.8.2 will support running the FRAPPA as a native
   triggered device and will eliminate the need to use Live Replay.


What is Live Replay
-------------------

MetaMorph's "Live Replay" feature is analogous to iQ's "Loop
Protocol".  One is waiting for an event to occur at an unknown time
point and data must be collected before and after that event.

Live Replay fills a circular buffer with as many images as set in
"Before the capture point".

.. warning::

   Timestamps are inaccurate using "Live Replay"; running the same
   experiment can generate different time intervals in the metadata.


Steps to run an experiment
**************************

1. Select your objective in the "Mag:" drop-down (this is essential
   for the correct FRAPPA calibration to be used)
2. Review / change your FRAP settings with the "Change Frappa
   Settings" Taskbar button.  If you don't see this button, click on
   the "FRAPPA" button to switch to the FRAPPA Taskbar.
3. Draw and save your FRAPPA region(s):

  a. Snap an image and draw your region(s).
  b. Save your regions by clicking "Save ROI(s) for FRAPPA" in the
     Taskbar.
  c. If your regions are large or you have set a long dwell time in the
     FRAP Settings check how long the bleach time is by opening the
     "FRAPPA Targeted Illumination" window from the Acquire menu.  The
     bleach "Approximate duration" is toward the bottom under the
     "Location" tab.

4. Open the Acquire > Acquire window.
5. Make sure "Camera State" is Overlapped under the Special tab (it
   will also work Non-Overlapped, but won't be as fast).
6. Click on the "Live Replay" tab.
7. Make sure "Enable Live Replay" is checked.
8. Review / change your acquisition settings under the "Live Replay"
   tab:

  a. The value of "Before the capture point" should contain enough
     images to capture BOTH the pre-bleach baseline images as well as
     the bleaching event itself (the duration you found in step 3c
     above).

9. Start Live.
10. Press "Stream+FRAP in Live Replay" taskbar button.

