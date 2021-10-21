# Example of missing strip for clang-10 On Ubuntu 20.04 with cmake > 3.21
# It can be demonstrated by running bash README.sh

rm -rf build
export CXX=clang++-10
cmake -S . -B build
cmake --build build


# First target that fails stripping
cd build
cmake --install . --strip --prefix foo
file foo/bin/test

# Second target that fails stripping
cmake --build . --target package
unzip test-0.1.1-Linux.zip
file test-0.1.1-Linux/bin/test

