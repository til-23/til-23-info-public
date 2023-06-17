.. _apis:

Provided API Services
~~~~~~~~~~~~~~~~~~~~~

To get started with the finals challenge, you will need to clone and install the python code 
given in this repo: 
`finals challenge github repo <https://github.com/til-23/til-23-finals-public>`_.

During the live robotics run, important services can be accessed via APIs through the ``tilsdk`` package.
The robot will have to communicate its findings/results to a remote “HQ” via the ReportingService API and it 
tracks its location and rotation through a “GPS system” via the LocalizationService API.

Below, we descibe at a high-level, two classes that participants 
*must* use: LocalizationService_ and ReportingService_. To see the *full* API documentation 
follow the instructions in the repo link above to generate the html docs. You are 
**highly encouraged** to generate and read the API docs.


.. figure:: _static/img/finals/System Architecture-Actual.png
   :alt: System Architecture for Physical Setup
   :align: center

   System Architecture (Physical Setup)


.. _LocalizationService:

Localization Service
####################


.get_pose()
-----------

The get_pose() method provides the robot's current estimated pose from a camera-based localisation system.

.. tip::
    To use the SDK to obtain the current estimated robot pose see :py:meth:`tilsdk.localization.LocalizationService.get_pose`

    Example:

    .. code-block:: python

        from tilsdk.localization import LocalizationService

        loc_service = LocalizationService()

        pose = loc_service.get_pose()


======================= ========= ====== ========================================================================
Field name              Type      Units  Remarks                                                                 
======================= ========= ====== ========================================================================
``pose.x``              float     metres x-coordinate of robot location relative to arena.                       
``pose.y``              float     metres y-coordinate of robot location relative to arena.                       
``pose.z``              float     degree Robot heading relative to arena, measured clockwise from x-direction.   
======================= ========= ====== ========================================================================

.. warning:: 
    Do not use the pose information available from the Robomaster SDK. Such pose information is a result of 
    dead-reckoning and is not aligned to our arena frame. It will not be compatible with our challenge
    services. Use the pose information provided by our Localization Service.


.get_map()
----------

The get_map() method provides a grid-based map representation.

Grid elements are square and represented by a float. Value indicates distance from nearest obstacle. Value <= 0 indicates occupied, > 0 indicates passable.
Grid is centered-aligned, i.e. real-world postion maps to center of grid square.

This map does not change throughout a run, so it only needs to be retrieved once.

.. tip:: 
    To use the SDK to get the map, see :py:meth:`tilsdk.localization.LocalizationService.get_map`.

    Example:

    .. code-block:: python

        from tilsdk.localization import LocalizationService

        loc_service = LocalizationService()

        map_ = loc_service.get_map()


============= ========= ========= ================================================================================================================================================================================== 
Field name    Type      Units        Remarks                                                                                                                                                                           
============= ========= ========= ================================================================================================================================================================================== 
``scale``     float     m/px      Scale of the grid image. A scale of n means each *pixel* in the grid image represents *n X n* meters on the physical arena.                                                       
``grid``      string    N/A       Base64 encoded grid image, the value of each pixel indicates the occupancy of that cell. The image is black (value=0) for empty cells and white (value=255) for occupied cells.   
============= ========= ========= ================================================================================================================================================================================== 


.. _ReportingService:

Reporting Service
#################

The reporting service can be regarded as a "HQ" that the autonomous robot must report to.
For the purposes of the competition, it is an answer submission service and it also
influences the taskings of the robot.

.. tip:: 
    To use the SDK to report robot status and submit answers to tasks, see ``tilsdk.reporting.service.ReportingService``.

    Example:

    .. code-block:: python

        from tilsdk.reporting import ReportingService

        ...

        rep_service = ReportingService(host='localhost', port=5501)  
        # Remember to change the host and port values to match the actual remote server.
    
        response = rep_service.start_run()  # This must be called before other ReportingService methods are called. 
        ...

        return_val = rep_service.check_pose(pose)
        # Call this to check if the robot is currently at a task or detour checkpoint.

        # use the ReportingService's report_situation, report_audio and report_digit methods to
        # submit answers and receive instructions at the Task checkpoint. 

        
        response = rep_service.end_run()
        # Call this only after receiving confirmation from the scoring server that you have reached the maze's last 
        # checkpoint.

.. _reporting-service-details:

