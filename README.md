>Installing the Python Wrapper

# Easy Way
Please follow these instructions to prepare XGBoost for use with Python. I am placing xgboost in a directory called `xgboost_install_dir` but this can be anything. (have a look at the [image](https://github.com/AdityaSoni19031997/xgb_gpu_dll/blob/master/(shows%20the%20directory%20structure%20of%20mine)follow%20this%20in%20anti%20clockwise%20direction%20from%20bottom%20right.png) attached for the directory, starting from bottom left and anticlockwise)

- `git clone https://github.com/dmlc/xgboost.git xgboost_install_dir` ( will clone it into the directory ` xgboost_install_dir`, preferably place it inside the `Anaconda/Lib/`)
- copy `xgboost.dll` (downloaded from the g-drive link [here](https://drive.google.com/file/d/1LSD6Ueq5VFgOMq_4Lm96SKsMG8DBB9KP/view?usp=sharing)) into the `xgboost_install_dir\python-package\xgboost\directory`
- `cd xgboost_install_dir\python-package\`
- `python setup.py install`

> How do I use it?
To use the GPU algorithm add the single parameter:

# Python example
param['updater'] = 'grow_gpu'

# GPU Acceleration Demo(optional)

Demo can be run via this line (provided you are in the conda or apt terminal)
- Assuming you are in the directory(in my case, yours can be different depending on your dir name) `ProgramData/Anaconda3/Lib/xgboost_install_dir`
- run this from the shell `python ./demo/gpu_acceleration/cover_type.py` (warning it will take a couple of minutes depending on your download speed as it will download the dataset, easier way is to simply pass the parameter as shown above and build a model...)

---------------------------------------------------------------------------------------------------------
# Hard Way (from the docs)

Build `XGBoost`

To build XGBoost follow these steps:

- `git clone https://github.com/dmlc/xgboost.git`
- `cd xgboost`
- `git submodule init`
- `git submodule update`
- `mkdir build`
- `cd build`
- `C:\dev\cmake-3.6.2-win64-x64\bin\cmake.exe .. -G”Visual Studio 14 2015 Win64″`
- `Edit: For GPU support use command: C:\dev\cmake-3.6.2-win64-x64\bin\cmake.exe .. -G”Visual Studio 14 2015 Win64″ -DPLUGIN_UPDATER_GPU=ON -DCUB_DIRECTORY=..\..\cub-1.6.4`
- `C:\Program Files (x86)\MSBuild\14.0\Bin\msbuild.exe /t:Clean,Rebuild /p:Configuration=Release xgboost.sln`
