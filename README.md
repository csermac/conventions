## Language

All code and comments should be written in plain english and should avoid cross language inclusions.

## Coding Style and Naming Conventions

All python code should conform to the [pep8 style guide](https://www.python.org/dev/peps/pep-0008/).

Naming of variables, functions, class methods should be underscore separated lowercase e.g.: ``` test_variable, Class_Name.method(), def function()```.
Class naming should be underscore separated camelcase e.g.: ``` class Class_Name(object) ```. If the class name includes acronyms those should be all uppercase, e.g.: ``` class IR_Camera(object), class UAV_Controller(object) ```

C++ code should follow the same naming convention and the style described in the [google c++ style guide](https://google.github.io/styleguide/cppguide.html).
The only exception is the naming of private and protected class methods which should have a leading underscore instead of a trailing one, e.g.: ``` void _private_method(), int _protected_getter()```

## Units

Measurement units must follow the SI standard as defined in [nist guide for the use of the international system of units](https://physics.nist.gov/cuu/pdf/sp811.pdf)
