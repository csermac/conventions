## Language

All code and comments must be written in plain english and should avoid cross language inclusions. This is needed for better portability and, eventually, showcasing in the case of public projects or snippets.

## Coding Style and Naming Conventions

All python code should conform to the [pep8 style guide](https://www.python.org/dev/peps/pep-0008/).

Naming of variables, functions, class methods should be underscore separated lowercase e.g.: ``` test_variable, Class_Name.method(), def function()```.
Class naming should be underscore separated camelcase e.g.: ``` class Class_Name(object) ```. If the class name includes acronyms those should be all uppercase, e.g.: ``` class IR_Camera(object), class UAV_Controller(object) ```

C++ code should follow the same functions and classes naming conventions of the python coded and the also the style described in the [google c++ style guide](https://google.github.io/styleguide/cppguide.html).
The only exception is the naming of private and protected class methods which should have a leading underscore instead of a trailing one, e.g.: ``` void _private_method(), int _protected_getter()``` instead of ``` void private_method_(), int protected_getter_()```, this enhances the readability of the code and makes it easier to distinguish private methods from the public ones. 

## Units

Measurement units must follow the SI standard as defined in [nist guide for the use of the international system of units](https://physics.nist.gov/cuu/pdf/sp811.pdf)
