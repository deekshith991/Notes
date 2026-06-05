# C testing modules
## Criterion [Link](https://criterion.readthedocs.io/en/master/)

Installation
```bash
# Arch linux
sudo pacman -S criterion
```

### Add test
- ***SUITE*** : it is similar to a batch of tests that work on all the cases of a function that we want to test. Like division we need to check for 2 cases. One for Zero denominator and non-zero denominator.

```c
#include <criterion/criterion.h>

Test(divisionTest, nonZeroDenominator) {
    int result;
    cr_assert_eq(divide(2, 1, &result), 0);
    // here we get result 2 test passes no problem for this case
    cr_assert_eq(result, 2);
}

Test(divisionTest, zeroDenominator) {
    int result;
    cr_assert_eq(divide(2, 0, &result), -1);
}

// If your existing divide() intentionally aborts or 
// crashes on division by zero, Criterion also supports death tests:
Test(divisionTest, zeroDenominator, .signal = SIGFPE) {
    divide(2, 0);
}
```


