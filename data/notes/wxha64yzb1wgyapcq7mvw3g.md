

### Variable Names

- Name a private identifier with a leading underscore ( `_username`)
  - These items are not meant to be part of the public interface
  - They may just be managing some part of internal state
  - **CAN** be accessed via `obj._method_` but items flow to the bottom of the suggestions
- Name a strongly private identifier with two leading underscores (`__password`)
  - when viewing objects `dir(obj)` these methods are not depicted as
    - `__method`
  - But rather as `_obj__method`
    - This prevents collisions when in a subclass from `obj` wanting to re-use the `__method`name
  - **CANNOT** be accessed via `obj.__method` an AttributeError will be thrown and cant be found
    - Only way to find it is with the mangled name: `instance._obj__method` but not recommended
- Special identifiers in Python end with two leading underscores.
  - _A.K.A. Dunder methods (double under-score)_ `__main__`
