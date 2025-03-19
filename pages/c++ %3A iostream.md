# cout
- 是什么？
	- `std::cout` 是 C++ 标准库中的一个对象，用于标准输出。它是 `ostream` 类型的对象，通常用于将数据打印到控制台或终端。
	- ``` cpp
	  namespace std {
	      extern ostream cout;
	  }
	  ```
- 为什么？
	- `std::cout` 提供了方便和标准的方式来输出信息到控制台或终端，适用于调试、程序运行时的信息显示等多种场景。它的主要作用包括：
		- 打印变量值。
		- 输出字符串和其他数据类型的内容。
		- 控制程序的执行流程。
- 示例
- ``` cpp
  #include <iostream>
  
  int main() {
      int a = 10;
      std::cout << "Hello, World!" << std::endl;
      
      // 输出整数和字符串
      std::cout << "The value of a is: " << a << std::endl;
  
      // 多个数据输出，使用不同的分隔符
      float b = 3.14f;
      char c = 'A';
      std::cout << "a, b, c are " << a << ", " << b << ", " << static_cast<int>(c) << std::endl;
  
      return 0;
  }
  ```
- **注意！**
	- 如果输出流最后没有回车结尾，会导致额外输出一个`%`符号
-
-