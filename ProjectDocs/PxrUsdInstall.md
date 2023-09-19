## Pxr USD安装
pxr usd 的安装可以自己下载源码编译，也可以使用Nvidia编译好的。这里使用Nvidia编译好的

下载地址 https://developer.nvidia.com/usd#bin

## USD Manager 工具安装

下载地址 https://github.com/dreamworksanimation/usdmanager

- 将pxr usd安装包中/scripts/set_usd_env.bat拷贝一份到 usd manager根目录中

修改bat中的内容

``` bat
@echo off
pushd %~dp0
set USD_INSTALL_DIR=D:/usd.py310.windows
set USD_PYTHON_ENV_SCRIPT=D:/usd.py310.windows/scripts/set_usd_python_env.bat

if exist %USD_PYTHON_ENV_SCRIPT% (
    call "%USD_PYTHON_ENV_SCRIPT%"
)

set PATH=^
%USD_INSTALL_DIR%\lib;^
%USD_INSTALL_DIR%\plugin\usd;^
%USD_INSTALL_DIR%\bin;^
%PATH%

set PYTHONPATH=%USD_INSTALL_DIR%\lib\python;%PYTHONPATH%
set PXR_MTLX_STDLIB_SEARCH_PATHS=%USD_INSTALL_DIR%\libraries

popd

exit /b

:: Resolve path to absolute.
:: Param 1: Name of output variable.
:: Param 2: Path to resolve.
:: Return: Resolved absolute path.
:ResolvePath
    set %1=%~dpfn2
    exit /b
```

- 然后在usd manager根目录创建一个 UsdManager.bat的启动脚本


``` bat
@echo off
setlocal

call "%~dp0set_usd_env.bat"

pushd %~dp0

cmd /k python3 D:/usdmanager/scripts/usdmanager

popd

exit /b
```

- 最后运行UsdManager.bat就可以启动 usdmanager工具
