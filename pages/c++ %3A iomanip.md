# std::fixed
- 是什么？
	- 设置定点格式输出浮点数
	- 需要与std::setprecision(int)连用
- 示例
- ``` cpp
  cout<<fixed<<setprecision(2)<<*iter;
  ```