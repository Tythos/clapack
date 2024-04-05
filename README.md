# clapack

This is a GitHub-based mirror of the most recent (v3.2.1) CLAPACK release from the original .tar.gz CMake-configured download:

https://netlib.org/clapack/clapack-3.2.1-CMAKE.tgz

## Usage

Aside from a `.gitignore` and this `README.md`, no modifications have been made.

The standard CMake three-step (including testing) should work out of the box on all platforms:

```sh
> cmake -S . -B build
> cmake --build build
> ctest --test-dir build --config Debug
```

See the original `COPYING` and `README.install` files (included in this repository) for more specific licensing terms and build details.

## Roadmap

I have no plans to modify the underlying/original source code.

I do think it would be useful to support the build and installation of dynamic libraries.

This would likely involve modifications to multiple `CMakeLists.txt` files and related resources.
