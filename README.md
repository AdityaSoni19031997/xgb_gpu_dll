Installing the Python Wrapper

# Easy Way
Please follow these instructions to prepare XGBoost for use with Python. I am placing xgboost in a directory called `xgboost_install_dir` but this can be anything.

- `git clone https://github.com/dmlc/xgboost.git xgboost_install_dir` ( will clone it into the directory ` xgboost_install_dir`)
- copy `xgboost.dll` (downloaded from the repository) into the `xgboost_install_dir\python-package\xgboost\directory`
- `cd xgboost_install_dir\python-package\`
- `python setup.py install`

# Hard Way (from the docs)

Build XGBoost

To build XGBoost follow these steps:

- git clone https://github.com/dmlc/xgboost.git
- cd xgboost
- git submodule init
- git submodule update
- mkdir build
- cd build
- C:\dev\cmake-3.6.2-win64-x64\bin\cmake.exe .. -G”Visual Studio 14 2015 Win64″
- Edit: For GPU support use command: C:\dev\cmake-3.6.2-win64-x64\bin\cmake.exe .. -G”Visual Studio 14 2015 Win64″ -DPLUGIN_UPDATER_GPU=ON -DCUB_DIRECTORY=..\..\cub-1.6.4
- C:\Program Files (x86)\MSBuild\14.0\Bin\msbuild.exe /t:Clean,Rebuild /p:Configuration=Release xgboost.sln
