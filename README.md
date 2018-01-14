# MPAS
    you can visit at https://github.com/MPAS-Dev
## 安装pio
### 1.安装netcdf
    CPPFLAGS='-I/public/home/gclearn/LIBRARY/grib2/include -I/public/home/gclearn/LIBRARY/hdf5/include' LDFLAGS='-L/public/home/gclearn/LIBRARY/grib2/lib -L/public/home/gclearn/LIBRARY/hdf5/lib' CC=mpicc ./configure --prefix=/public/home/gclearn/LIBRARY/netcdf4c
    export LD_LIBRARY_PATH=/public/home/gclearn/LIBRARY/netcdf4c/lib:$LD_LIBRARY_PATH
    make && make install
    CPPFLAGS=-I/public/home/gclearn/LIBRARY/netcdf4c/include LDFLAGS=-L/public/home/gclearn/LIBRARY/netcdf4c/lib ./configure -prefix=/public/home/gclearn/LIBRARY/netcdf4c CC=mpicc FC=mpifort
    make && make install
    
### 2.安装pio
    export NETCDF_PATH=/public/home/gclearn/LIBRARY/netcdf4c
    CC=mpicc FC=mpifort ./configure -prefix=/public/home/gclearn/LIBRARY/pio --with-netcdf
    
    cmake版本
    CC=mpicc FC=mpifort cmake -DNetCDF_C_PATH=/public/home/gclearn/LIBRARY/netcdf4c -DNetCDF_Fortran_PATH =/public/home/gclearn/LIBRARY/netcdf4c -DPnetCDF_PATH=/public/home/gclearn/LIBRARY/pnetcdf -DPIO_HDF5_LOGGING=On -DPIO_USE_MALLOC=On
    
## 安装MAPS
    设置NETCDF PNETCDF PIO环境变量
    export NETCDF=/public/home/gclearn/LIBRARY/netcdf4c
    export PNETCDF=/public/home/gclearn/LIBRARY/pnetcdf
    export PIO=/public/home/gclearn/LIBRARY/pio
