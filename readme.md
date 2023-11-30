## 1.使用方法
推荐使用c++11标准使用此类
### 定义类型
std::shared_ptr<MemoryPool> m_memory_pool=nullptr;
### 初始化
	if (!m_memory_pool)
	{
		m_memory_pool = std::make_shared<MemoryPool>(length);
	}
其中length表示每次申请的内存大小
### 获取可用内存地址
 uint8_t* data= (uint8_t*)m_memory_pool->get();
### 返还内存给内存池
m_memory_pool->release(data);
## 2.注意
此内存池每次只能申请固定大小的内存，如果业务存在变长内存，需要考虑长度变化时，重新初始化内存，或使用其他方案。

