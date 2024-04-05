# clapack

This is a GitHub-based mirror of the most recent (v3.2.1) CLAPACK release from the original .tar.gz CMake-configured download:

https://netlib.org/clapack/clapack-3.2.1-CMAKE.tgz

## Modifications

Aside from a `.gitignore` and this `README.md`, no modifications have been made.

See the original `COPYING` and `README.install` files (included in this repository) for more specific licensing terms and build details.

## Usage

The standard CMake three-step (including testing) should work out of the box on all platforms, though unmodified I am only getting a 20% pass rate on Windows/MSVC:

```sh
> cmake -S . -B build
> cmake --build build
> ctest --test-dir build -C Debug
> cmake --install build --config Debug
```

The final step, which may require administrator privileges, will install the following headers:

* `include/blaswrap.h`

* `include/clapack.h`

* `include/f2c.h`

It will also install the following static libraries (using the Windows formatting with the default configuration, debug, for these examples):

* `libf2cd.lib`

* `blasd.lib`

* `lapackd.lib`

## Roadmap

I have no plans to modify the underlying/original source code.

- [ ] I need to demonstrate a "test" program that successfully links against this library on more problematic platforms (e.g., Windows/MSVC)

- [ ] It would be useful to verify the simplier demonstrations from the CLAPACK FAQ (https://www.netlib.org/clapack/faq.html)

- [ ] I do think it would be useful to support the build and installation of dynamic libraries. This would likely involve modifications to multiple `CMakeLists.txt` files and related resources.

- [ ] Ultimately, the success of these efforts will be determined by how well integrated they can be as an implementation for downstream bindings in a tensor library I use (e.g., as a drop-in replacement for OpenBLAS): https://github.com/xtensor-stack/xtensor-blas
