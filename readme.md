## 1.使用方法(Usage)
推荐使用c++11标准使用此类
It is recommended to user this class with the c++11 standard.
### 定义类型(Define the types)
std::shared_ptr<MemoryPool> m_memory_pool=nullptr;
### 初始化(Initialization)
	if (!m_memory_pool)
	{
		m_memory_pool = std::make_shared<MemoryPool>(length);
	}
其中length表示每次申请的内存大小
Here, length represents the size of memory to be allocated each time.
### 获取可用内存地址(Get the available memory address)
 uint8_t* data= (uint8_t*)m_memory_pool->get();
### 返还内存给内存池(Return memory to the memory pool)
m_memory_pool->release(data);
## 2.注意(Attention)
此内存池每次只能申请固定大小的内存，如果业务存在变长内存，需要考虑长度变化时，重新初始化内存，或使用其他方案。
This memory pool can only allocate fixed-size memory each time. If there is variable-length memory in your business logic, consider reinitializing the memory when the length changes or using other approaches.


### 

