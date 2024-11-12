The point of this repository is to illustrate how we can get into "flaky" situations with circular dependencies.

The situation is:

`left_package.lower -> right_package.right`
`right_package.right -> left_package.upper`

This means that *at a package level*, there is a circular dependency.  But with respect to individual modules, there is not a circular dependency.

This circular dependency is still bad because we do not have control over when `__init__.py`  will run.

I am personally surprised that `success.py` can actually run without crashing.


