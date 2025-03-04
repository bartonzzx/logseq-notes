# 参考
- [AOCL User Guide](https://docs.amd.com/r/en-US/57404-AOCL-user-guide/AOCL-User-Guide-57404)
- # 安装
- 参考user guide
- 安装完成显示
- ```bash
  collected includes  in the common include directory
  
  collected libs for da in the common lib directory
  
  'amd-libs.cfg' -> '/home/barton/aocl/5.0.0/aocc/amd-libs.cfg'
  AOCL available at: /home/barton/aocl/5.0.0/aocc
  -----------------------------------------------------------------------------------------------------------------------------
  Do you want to set LP64 or ILP64 libraries as default libraries? (Enter 1 for LP64 / 2 for ILP64 / Default option: 1)
  -----------------------------------------------------------------------------------------------------------------------------
  
  Setting LP64 libs as default
  ----------------------------------------------------------------------------------------------------
  AOCL INSTALLED SUCCESSFULLY AT: /home/barton/aocl/5.0.0/aocc/lib
  ----------------------------------------------------------------------------------------------------
  Steps to setup:
  ----------------------------------------------------------------------------------------------------
  Setup AOCL environment by executing the below command
  	source /home/barton/aocl/5.0.0/aocc/amd-libs.cfg
  ----------------------------------------------------------------------------------------------------
  To set AOCL environment via module system
  	cd /home/barton/aocl/5.0.0/aocc
  	module load ./aocl-linux-aocc-5.0.0_module
  
  To unset AOCL environment via module system
  	cd /home/barton/aocl/5.0.0/aocc
  	module unload ./aocl-linux-aocc-5.0.0_module
  ----------------------------------------------------------------------------------------------------
  
  ```