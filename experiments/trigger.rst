Streaming with Mosaic (using Stream Acquisition)
================================================

To watch bleaching, we use the "Trigger component positions at
specific frames" function of Acquire >  Stream Acquisition...

MetaMorph's uber powerful Multidimensional Acquisition (MDA) module is
does not allow running journals (and thus using the Mosaic) during a
stream; only at he beginning or end.

1. Select your objective in the "Mag:" drop-down, and the select the
   matching Mosaic calibration in the Targeted Illumination Window
   "Location" tab.
2. Draw and upload your Mosaic mask:

  a. Draw your region(s).

  b. Save your regions by clicking "Active Region" in the Location tab
     of the Targeted Illumination window, and then click "Update
     Device Mask.

  c. Click "LatestMask" to complete programming the Mosaic.

.. image:: /images/calibration/mosaic02_setup_roi.png

3. Open the Acquire > Stream Acquisition window.  Make sure "Trigger
   components at specific frames" is checked.

.. image:: /images/calibration/mosaic01_stream_setup.png

4. Make sure "Camera State" is Overlapped under the Camear Parameters
   tab (it will also work Non-Overlapped, but won't be as fast).

.. image:: /images/calibration/mosaic04_stream_setup.png

5. Click on the Trigger tab:

  a. Make sure the Component is set to "Photonic Instruments Mosaic
     Mask" and the Position to "Pulse".

  b. Set the trigger time point to pulse the Mosaic and add the
     "Trigger move".

.. image:: /images/calibration/mosaic03_stream_setup.png

6. Click "Acquire".
