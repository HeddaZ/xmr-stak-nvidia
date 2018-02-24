# Compile **xmr-stak** -- Hedda

## Install CMake

- download and install the latest version from [https://cmake.org/download/](https://cmake.org/download/)
- tested version: [cmake 3.9](https://cmake.org/files/v3.9/cmake-3.9.0-rc3-win64-x64.msi)
- during the install choose the option `Add CMake to the system PATH for all users`

## Compile

- download and unzip `xmr-stak-nvidia`
- open the command line terminal `cmd`
- `cd` to your unzipped source code directory
- execute the following commands
  ```
  "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsMSBuildCmd.bat"
  set CMAKE_PREFIX_PATH=D:\Workspace\CPP\xmr-stak-nvidia\libs\hwloc;D:\Workspace\CPP\xmr-stak-nvidia\libs\libmicrohttpd;D:\Workspace\CPP\xmr-stak-nvidia\libs\openssl
  mkdir build
  cd build
  cmake -G "Visual Studio 15 2017 Win64" -T v140,host=x64 ..
  msbuild xmr-stak-nvidia.sln /p:Configuration=Release
  cd bin\Release
  copy ..\..\..\config.txt .
  ```
- customize your `config.txt` file by adding the pool, username and password
