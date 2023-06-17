Definitions for robot localization and movement
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Reference frames
################

Please see the diagram below to understand the definitions of the spatial axes used in this challenge.

.. figure:: _static/img/finals/ref_frames.svg
    :width: 500px
    :align: center

    Definitions of axes. "Arena" above refers to the physical arena. Info from the LocalizationService
    is in the arena frame. "Body" refers to the Robot. The RoboMaster SDK is with respect to the Body frame.
    Note that the robot's x-axis is its forward axis, while the y-axis is its right-facing axis.


Location, Orientation & Pose
############################

A **Location** is a 2-dimensional point on the plane of the **arena** and is a 2-tuple 
(representing the x and y coordinates on the plane).

**Orientation** (a.k.a. **heading**) is with respect to the **arena's** X-axis. It is given in 
*decimal degrees* and is the angle between the Body's forward axis relative to the arena's 
``X``-axis. Counter-clockwise from the arena's X-axis is positive, while clockwise from the 
arena's X-axis is negative.

.. NOTE::
    The Body frame's ``z``-axis points downwards per the DJI Robomaster convention.
    Therefore a positive heading in the arena frame is a negative 
    heading in the body frame.

A **Pose** is a 2-dimensional location *AND* a 1-dimensional orientation, and is a 3-tuple of 
(x-coordinate, y-coordinate, heading). Keeping with the convention used in the DJI Robomaster SDK, 
heading angle is in *degrees* and is represented by the attribute/parameter ``z``.

.. important::
    All locations and poses used by the LocalisationService and ReportingService are given in the *arena* frame.

.. important::
    All API parameters and return values in the Robomaster SDK are in the *body* frame.