# CPP PRINTING

## Summary

Notes on cpp printing with functions like `printf()`, `cout`, `puts()`, etc

## Resources

[Differences](https://www.includehelp.com/cpp-tutorial/difference-between-cout-and-puts.aspx)

## `puts()`

Can only print strings. Use `cout` or another variant for numbers.
Have to flush manually

```cpp
#include <iostream>
#include <stdio.h>

int main()
{
	std::puts("Hello World\n");
	fflush(stdout);
	return 0;
}
```

## `cout`

```cpp
#include <iostream>

int main()
{
	std::cout<<"Hello World"<<endl;
	return 0;
}
```

#### boolean printing

```cpp
#include <iostream>
#include <iomanip>

int main() {
    std::cout<<false<<"\n";
    std::cout << std::boolalpha;
    std::cout<<false<<"\n";
    return 0;
}
```
