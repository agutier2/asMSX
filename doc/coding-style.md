
# asMSX coding style

If you want to contribute to asMSX, please consider following our shared guildelines for coding style

## 1. Set your editor to use tabs and show them as 4 spaces

In vim, add following lines to your `.vimrc`:

    set tabstop=4
    set shiftwidth=4
    set noexpandtab

Visual Studio seems to come with those settings by default.

## 2. Highlight tabs, spaces, cr and lf explicitly if you can

In vim, add those lines to your `.vimrc` to highlight spaces and tabs:

    syntax on
    set syntax=whitespace

In Visual Studio, press `Ctrl+R` and `Ctrl+W`.

## 3. Use Allman brackets

```
function samplef(int a, int b, int c, int d)
{
    if (a == 1)
    {
        a_function();
        if (b == 50)
            c = 100;
    }
    else if ((a == BBB) && (d != 0))
    {
        another_function();
	c = 200;
    }
    else
    {
        fprintf(stderr, "Unexpected value found: %d\n", a);
        exit(1);
    }
}
```

1. Curly brackets are on their own line and start at the begining of the block.
2. Don't add comments after curly brackets, put them above or below please.
3. If you want to use `if () {} else if () {} else {};`, put `else if` and `else` on a separate line,
idented same as starter `if`.
4. If you have more then a couple of `else if`, consider using `switch()` instead.
5. If block consist of single statement, don't use curly brackets, unless it is a very convoluted,
deeply nested 'if/else if/else' code or you have some other reasons to beleive it will improve clarity.
6. C99 `<stdint.h>` types are preferred, but plain C89 char/int/long with optional signed/unsigned qualifier are acceptable.
7. Only do typecasts when necessary.
8. Try to address all the compiler warnings in your code: remove unused variables, avoid using uninitialized variables etc.
9. Once the project starts using gtest/ctest, please add test units to cover new or changed code in your patch.
10. Use static checking tools that are available: enable all the warnings in compiler, use a linter in Linux/BSD,
use [cppcheck](http://cppcheck.sourceforge.net/) and Visual Studio Code Analysis tool on Windows.
11. If you can do it, please build your code on as many platforms as possible:
Visual Studio 2017 on Windows 10, gcc on Linux, clang on BSD and Mac etc.
Sometimes you'll find that header you think is everywhere, isn't everywhere.
12. Consider reading John Carmack's article [In-depth: Functional programming in C++](http://www.gamasutra.com/view/news/169296/Indepth_Functional_programming_in_C.php).
It works well for plain C programs too.
13. Consider reading [How to C in 2016](https://matt.sh/howto-c). Good tips.
14. [List of verifications tools](https://stackoverflow.com/questions/413477/is-there-a-good-valgrind-substitute-for-windows).
