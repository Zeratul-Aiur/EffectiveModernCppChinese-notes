# 智能指针

## 条款十八：对于独占资源使用 std::unique_ptr

- `std::unique_ptr`是典型的只可移动的对象，移动一个`std::unique_ptr`将会发生内存所有权（实际上就说其持有的裸指针）的转移。

## 条款十九：对于共享资源使用 std::shared_ptr

- `std::shared_ptr`用于多个指针需要

## 条款二十：当 std::shared_ptr 可能悬空时使用 std::weak_ptr

## 条款二十一：优先考虑使用 std::make_unique 和 std::make_shared，而非直接使用 new

## 条款二十二：当使用 Pimpl 惯用法，请在实现文件中定义特殊成员函数
