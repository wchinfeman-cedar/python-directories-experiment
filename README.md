The point of this repository is to illustrate how we can get into "flaky" situations with circular dependencies.

**In particular, this illustrates how the _removal_ of a dependency can cause Python to begin complaining about a "new" Circular Dependency**

The situation is:

`left_package.lower -> right_package.right`

while

`right_package.right -> left_package.upper`

This means that *at a package level*, there is a circular dependency.  But with respect to individual modules, there is not a circular dependency.

This circular dependency is still bad because we do not have control over when `__init__.py`  will run.

I am personally surprised that `success.py` can actually run without crashing.


