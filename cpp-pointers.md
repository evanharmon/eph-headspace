# CPP POINTERS

## Summary

Notes on working with pointers in c++

## Resources

[Smart Developers Smart Pointers](https://www.fluentcpp.com/2017/08/22/smart-developers-use-smart-pointers-smart-pointers-basics/)
[CPP REF Smart Pointers](https://en.cppreference.com/book/intro/smart_pointers)
[LEARNCPP Dynamic Memory Allocation](https://www.learncpp.com/cpp-tutorial/69-dynamic-memory-allocation-with-new-and-delete/)

## Smart Pointers

used to make sure an object is deleted if no longer referenced. Helpful in preventing memory leaks

Three Types:
std::unique_ptr
std::shared_ptr
std::weak_ptr

#### Unique Pointer

Deleted at function end or through an exception

- Does not support copying
- Supports move semantics

Move unique_ptr

```cpp
std::unique_ptr<int> valuePtr(new int(15));
std::unique_ptr<int> valuePtrNow(std::move(valuePtr));
```

#### Shared Pointer

Used to store and pass a reference beyond the scope of a function

- Reference Counting Pointer

[Example](https://en.cppreference.com/book/intro/smart_pointers)

```cpp
#include <memory>

class Foo
{
	public void doSomething();
};

class Bar
{
private:
	std::shared_ptr<Foo> pFoo;
public:
	Bar()
	{
		pFoo = std::shared_ptr<Foo>(new Foo());
	}

	std::shared_ptr<Foo> getFoo()
	{
		return pFoo;
	}
};
```

## Delete Pointer

Return a dynamically allocated piece of memory back to the OS

```cpp
delete myptr;
myptr = nullptr;
```

## Dangling Pointer

Pointer that is pointing to deallocated memory. Dereferencing or deleting a
dangling pointer leads to undefined behavior.

Set deleted pointers to nullptr after deleting unless they are going out of
scope immediately after.
