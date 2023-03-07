
An example of C++ project with pybind11 bindings

Project layout
--------------


.. code-block:: sh

    ./include/cpp_library/     # includes (.h) of C++ project
    ./src/                     # sources (.cpp) of C++ project
    ./cpp_library_bindings/    # pybind11 bindings of C++ project

Build module shared library
---------------------------

Needed only for testing/debug

.. code-block:: sh

    mkdir build
    (cd build ; cmake .. )


Install python
--------------

The build step will be invoked automatically during install process

.. code-block:: sh

    pip install .  # regular python install is working
