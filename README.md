EasyPkg
-------

A Julia package to simply package development.


Package Source code
-------------------

Use `EasyPkg.include_sources(name...)` to shorten code to include package
source files a little. Given a package structure like

* src
    * foo/foo.jl
    * foo/xyz.jl
    * bar.jl

use

```julia
EasyPkg.include_sources(
	"foo",
	"bar",
)
```

to include "foo/foo.jl" and "bar.jl". Obviously, "foo/foo.jl" will be
responsible for including "foo/xyz.jl" and other files in the "foo"
subdirectory (e.g using `EasyPkg.include_sources` again).


Package Tests
-------------

Use `EasyPkg.run_all_tests()` reduces the average Julia project's
"runtests.jl" to

```julia
import EasyPkg
EasyPkg.run_all_tests()
```