# aws-sigv4-cpp
C++ implementation of AWS Signatrue V4 for signing API request

Original fork is from https://github.com/zxwind/aws-sigv4-cpp

Updated to C++17 by J. Koutavas


If you want to make googletest, instead of using the googletest included with the original fork of this repository, do the following:

````
$ git clone https://github.com/google/googletest
$ cd googletest
$ mkdir install
$ cd install
$ cmake -DCMAKE_CXX_COMPILER="c++" -DCMAKE_CXX_FLAGS="-std=c++11 -stdlib=libc++" ../
$ make
$ sudo make install
````

Then, if you want to smoke test googletest itself, do this:
````
$ mkdir ~/smoketest
$ cd ~/smoketest
$ cp {googletest-clone}/samples/sample1.cc
$ cp {googletest-clone}/googletest/samples/sample1.cc .
$ cp {googletest-clone}/googletest/samples/sample1.h .
$ cp {googletest-clone}/googletest/samples/sample1_unittest.cc .
$ cp {googletest-clone}/googletest/src/gtest_main.cc .
$ g++ -std=c++11 -stdlib=libc++  sample1_unittest.cc sample1.cc gtest_main.cc -lgtest -lpthread -o sample1 
$ ./sample1
````

I've added a "tests/awsv4_test.xcodeproj" that runs aws-sigv4-cpp tests using googletest as described above. This xcode project depends on openssl having been isntalled by brew.