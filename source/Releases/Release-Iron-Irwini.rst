.. _upcoming-release:

.. _iron-release:

.. move this directive when next release page is created

ROS 2 Iron Irwini (codename 'iron'; May, 2023)
==============================================

.. contents:: Table of Contents
   :depth: 2
   :local:

*Iron Irwini* is the ninth release of ROS 2.
What follows is highlights of the important changes and features in Iron Irwini since the last release.

Supported Platforms
-------------------

Iron Irwini is primarily supported on the following platforms:

Tier 1 platforms:

TBD

Tier 2 platforms:

TBD

Tier 3 platforms:

TBD

For more information about RMW implementations, compiler / interpreter versions, and system dependency versions see `REP 2000 <https://www.ros.org/reps/rep-2000.html>`__.

Installation
------------

To come.

New features in this ROS 2 release
----------------------------------

Service Introspection
^^^^^^^^^^^^^^^^^^^^^

Services can now be echoed using ``ros2 service echo`` and recorded via ``ros2 bag record --services``.

* `REP2012: Service Introspection`_.

   .. _`REP2012: Service Introspection`: https://github.com/ros-infrastructure/rep/pull/360


rosidl fixes
^^^^^^^^^^^^

Packages defining actions no longer need to ``<depend>`` on the action_msgs package.



Changes since the Humble release
----------------------------------

rmw
^^^
- RMW_GID_STORAGE_SIZE: Changed from 24 to 16 (`rmw#328`_)

.. _`rmw#328`: https://github.com/ros2/rmw/pull/328

rcl
^^^

- Services and clients take a clock handle in their respective options struct if service introspection is to be enabled (`rcl#997`_)

.. _`rcl#997`: https://github.com/ros2/rcl/pull/997

rosidl
^^^^^^

- ``rosidl_defaults`` has been split into ``rosidl_core`` and ``rosidl_defaults`` to correct dependency loops (`rosidl_defaults#22`_)
- Services now generate a new ``_Event`` message

    - ``rosidl_service_typesupport_t`` now includes methods for creating and destroying said event message (`rosidl#700`_)

.. _`rosidl#700`: https://github.com/ros2/rosidl/pull/700
.. _`rosidl_defaults#22`: https://github.com/ros2/rosidl_defaults/pull/22


Known Issues
------------

To come.

Release Timeline
----------------

    November, 2022 - Platform decisions
        REP 2000 is updated with the target platforms and major dependency versions.

    By January, 2023 - Rolling platform shift
        Build farm is updated with the new platform versions and dependency versions for Iron Irwini (if necessary).

    Mon. April 10, 2023 - Alpha + RMW freeze
        Preliminary testing and stabilization of ROS Base [1]_ packages, and API and feature freeze for RMW provider packages.

    Mon. April 17, 2023 - Freeze
        API and feature freeze for ROS Base [1]_ packages in Rolling Ridley.
        Only bug fix releases should be made after this point.
        New packages can be released independently.

    Mon. April 24, 2023 - Branch
        Branch from Rolling Ridley.
        ``rosdistro`` is reopened for Rolling PRs for ROS Base [1]_ packages.
        Iron development shifts from ``ros-rolling-*`` packages to ``ros-iron-*`` packages.

    Mon. May 1, 2023 - Beta
        Updated releases of ROS Desktop [2]_ packages available.
        Call for general testing.

    Mon. May 15, 2023 - Release Candidate
        Release Candidate packages are built.
        Updated releases of ROS Desktop [2]_ packages available.

    Thu. May 18, 2023 - Distro Freeze
        Freeze rosdistro.
        No PRs for Iron on the ``rosdistro`` repo will be merged (reopens after the release announcement).

    Tue. May 23, 2023 - General Availability
        Release announcement.
        ``rosdistro`` is reopened for Iron PRs.

.. [1] The ``ros_base`` variant is described in `REP 2001 (ros-base) <https://www.ros.org/reps/rep-2001.html#ros-base>`_.
.. [2] The ``desktop`` variant is described in `REP 2001 (desktop-variants) <https://www.ros.org/reps/rep-2001.html#desktop-variants>`_.

Development progress
--------------------

For progress on the development and release of Iron Irwini, see `the tracking GitHub issue <https://github.com/ros2/ros2/issues/1298>`__.

For the broad process followed by Iron Irwini, see the :doc:`process description page <Releases/Release-Process.rst>`.
