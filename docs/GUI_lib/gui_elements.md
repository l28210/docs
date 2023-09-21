# gui用法

The Elements project is set up so that you can easily copy and paste any of the examples outside the project, set -DELEMENTS_ROOT=”path/to/elements”, and the example should immediately build without any hassle.

Here’s an example for XCode assuming the elements lib is in the same directory alongside the “hello_universe” example directory you copied to:

Copy the hello_universe example project directory.
Make a build directory inside the hello_universe directory.
CD to the build directory.
cmake -GXcode -DELEMENTS_ROOT="../elements" ../
