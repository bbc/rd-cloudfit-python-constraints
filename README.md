# ARCHIVED
This repository is archived and is no longer being maintained.

# rd-cloudfit-python-constraints
A location for the constraints file used in building cloudfit services

The only file of importance in this repo is [constraints.txt] which is a pip-formatted constraints file.

## Guide to adding constraints to the file

Every python package you create should have a setup.py, and the setup.py should list all of the *direct* dependencies of the package. Indirect dependencies should not be added to the setup.py file.

* Dependencies of the form: `package-name` or `package-name >= {version}` do not need to be copied into the constraints file.
* Dependencies that make use of the `<`, `<=`, `==` or `~=` notations must be duplicated in the constraints file as well as in the setup.py
* If the same package already has a constraint listed in the constraints file when you need to add one then make sure you combine the two constraints together into a single constraint. If this isn't possible then we have a problem since the packages clash with each other.


If any packages you directly depend upon also have their own dependencies which would need to be included in the constraints file then you will need to add them to the constraints file as well.