# grtest
Minimalist C/C++ testing framework with CMake integration.

## Usage
Add grtest to `.gitmodules`
```ini
[submodule "grtest"]
	path = "grtest"
	url = https://github.com/v0lat1le/grtest
```
Use grtest to define test cases
```cpp
#include "grtest.h"

TEST_CASE(test_addition) {
    assert(2+2 == 4);
}

TEST_CASE(test_multiplication) {
    assert(2*2 == 4);
}
```
## CMake integration
Include grtest in top-level `CMakeLists.txt`
```cmake
enable_testing()
add_subdirectory(grtest)
```
Add CTest executable
```cmake
add_executable(my_test "test/my_test.cpp")
target_link_libraries(my_test PRIVATE grtest)
grtest_discover_tests(my_test)
```
