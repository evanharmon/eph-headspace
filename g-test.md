# G TEST

## Summary

Notes on using google test

## Resources

- [Github](https://github.com/google/googletest)
- [Primer](https://github.com/google/googletest/blob/master/googletest/docs/primer.md)
- [Google Mock](https://github.com/google/googletest/blob/master/googlemock/README.md)
- [Readme](https://github.com/google/googletest/blob/master/googletest/README.md)
- [G Test Parallel](https://github.com/google/gtest-parallel)

## Assertions

- [Docs](https://github.com/google/googletest/blob/master/googletest/docs/primer.md)

`ASSERT_*` generates fatal failures and aborts current function

## Expects

- [Docs](https://github.com/google/googletest/blob/master/googletest/docs/primer.md)

`EXPECT_*` generates non-fatal failures and does not abort current function.
Use `EXPECT_*` to show for multiple failures for a test
