metismex for Windows
========

Based on [metismex](https://github.com/dgleich/metismex.git)


Compiling
---------

The following instructions worked on Windows 10, Visual Studio 2017 and MATLAB R2019b.
For UNIX, see [metismex](https://github.com/dgleich/metismex.git).

1. Make sure you have a working version of `cmake` installed.
  
2. Compile metis.
      
        # in the metis-5.0.2 directory
        mkdir build
        cd build
        cmake -A x64 ..
        cmake --build . --config Release
    
3. Compile metismex. Start MATLAB and cd to metismex folder.
        
        # in the metis-5.0.2/metismex directory
        >> make

4. Check that it works

        >> A = blkdiag(ones(5),ones(5)); A(1,10) = 1; A(10,1) = 1; A(5,6) = 1; A(6,5) = 1;
        >> [p1,p2] = metispart(sparse(A))
        
        p1 =
        
             6     7     8     9    10
        
        
        p2 =
        
             1     2     3     4     5

