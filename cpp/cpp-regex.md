# CPP REGEX

## Summary

Notes on using regex in C++

## Resources

## Regex Replace

[Replace Docs](http://www.cplusplus.com/reference/regex/regex_replace/)

```cpp
std::string s ("there is a subsequence in the string\n");
std::regex e ("\\b(sub)([^ ]*)");   // matches words beginning by "sub"

// using string/c-string (3) version:
std::cout << std::regex_replace (s,e,"sub-$2");

// using range/c-string (6) version:
std::string result;
std::regex_replace (std::back_inserter(result), s.begin(), s.end(), e, "$2");
std::cout << result;

// with flags:
std::cout << std::regex_replace (s,e,"$1 and $2",std::regex_constants::format_no_copy);
std::cout << std::endl;
```

## Regex Search

```cpp
std::cout << std::regex_search("-123", e) << std::endl;
```
