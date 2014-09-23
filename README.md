appium-and-py.test
==================

Figuring out the best practices for Appium testing when using py.test fixtures.

Rationale
---------

The one thing I want to do with my [`Appium` tests](http://appium.io/) is to be able to parametrize them via the command line. Searching the [`nosetests` documentation](https://nose.readthedocs.org/en/latest/index.html), I couldn't see (within 5 minutes of starting the search) how to do it.

This is particularly important for integration testing, where I might have a handful of different Android or iOS devices, and would like to just run the same test suite across them all. I don't want to hardcode this using [`nose`'s test generators](https://nose.readthedocs.org/en/latest/writing_tests.html#test-generators), I just want to control which device is used via the command line.

Doing this with `py.test` seems to be possible, using the dependency-injected fixture mechanisms described in the [`py.test` Basic patterns and examples](http://pytest.org/latest/example/simple.html). But getting this right also means some boilerplate needs to be created. 

So that's what is here, the basic framework for some Appium tests on a defined table of devices.
