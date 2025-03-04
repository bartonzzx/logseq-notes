# 参考
- [Quickstart](https://langchain-ai.github.io/langgraph/tutorials/introduction/)
- # 分析
- ## Annotated注解
- 是什么：
- ```python
  # 基本语法
  from typing import Annotated
  
  Annotated[BaseType, Metadata]
  
  BaseType ：这是主要的类型，表示变量的基本类型。例如，list、str、int 等。
  Metadata ：这是附加的元信息，可以是任何对象（如函数、字符串、类等）。
  	它不会影响运行时的行为，但可以在静态分析或框架中使用。
  Annotated 的核心思想是：在不改变基础类型的情况下，为类型添加额外的上下文信息。
  ```
- 使用示例：
- ```python
  # 使用示例
  from typing import Annotated
  
  # Define a function to process metadata
  def validate_positive(value):
      if value <= 0:
          raise ValueError("Value must be positive")
      return value
  
  # Use Annotated to attach metadata
  PositiveInt = Annotated[int, validate_positive]
  
  # Example usage
  def process_value(x: PositiveInt):
      print(f"Processing value: {x}")
  
  # Valid input
  process_value(10)
  
  # Invalid input (raises an error)
  process_value(-5)
  ```
- ## TypedDict
- 是什么：
- ```python
  from typing_extensions import TypedDict
  
  class Person(TypedDict):
      name: str
      age: int
      is_student: bool
      
  TypedDict 允许你定义一个字典类型，其中每个键都有明确的类型注解。
  	与普通的 dict 不同，TypedDict 提供了以下优势：
  
  类型安全 ：可以在静态类型检查器（如 mypy）中捕获键名或值类型的错误。
  文档化 ：通过定义键和值的类型，可以更清晰地表达数据结构的意图。
  兼容性 ：对于需要严格类型检查的项目，TypedDict 是一种优雅的解决方案。
  ```
- 使用示例：
- ```python
  # 为TypedDict传入参数total
  class OptionalPerson(TypedDict, total=False):
      name: str
      age: int
      is_student: bool
      address: str  # 可选字段
  ```
- # 步骤
- 设置API_KEY
  logseq.order-list-type:: number
- logseq.order-list-type:: number