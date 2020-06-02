# CPP STRING

## Summary

Notes on working with strings in C++

## Resources

## Cast Int To String

```cpp
std::to_string(121)
```

## Convert String To Int

[Geeks](https://www.geeksforgeeks.org/converting-strings-numbers-cc/)

```cpp
int i = std::stoi("10");
int i = std::stol("1013433");
int i = std::stoll("2147483648");
```

## Get Length Of String

```cpp
std::string str ("Test string");
std::cout << "The size of str is " << str.length() << " bytes.\n";
```

## Reverse A String

[Examples](https://www.geeksforgeeks.org/reverse-a-string-in-c-cpp-different-methods/)

```cpp
std::reverse(copy.begin(), copy.end());
```

## Join Strings

```cpp
auto sign = "-";
auto sint = "123";
auto joinedInt = sign + sint;
```
