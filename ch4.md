# 智能指针

## 条款十八：对于独占资源使用 std::unique_ptr

- `std::unique_ptr`是典型的只可移动的对象，移动一个`std::unique_ptr`将会发生内存所有权（实际上就说其持有的裸指针）的转移。

## 条款十九：对于共享资源使用 std::shared_ptr

- `std::shared_ptr`用于多个指针需要共同管理一个内存对象的情形。
- 除了持有裸指针外，还通过一个控制块来管理引用计数等信息。引用计数的递增和递减必须是原子操作。
- 避免从同一个裸指针出发构造多个`std::shared_ptr`。

## 条款二十：当 std::shared_ptr 可能悬空时使用 std::weak_ptr

- 主要用于打破`std::shared_ptr`的循环引用。

## 条款二十一：优先考虑使用 std::make_unique 和 std::make_shared，而非直接使用 new

- 对于希望指定自定义析构器的场景，不适合使用 make。
- make 系列函数对形参进行完美转发的代码使用的是小括号初始化，因此在使用`initializer_list`初始化的场景可能不行。

## 条款二十二：当使用 Pimpl 惯用法，请在实现文件中定义特殊成员函数
