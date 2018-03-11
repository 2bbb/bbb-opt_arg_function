# bbb::opt_arg_function

```
     _/        _/        _/
    _/_/_/    _/_/_/    _/_/_/
   _/    _/  _/    _/  _/    _/
  _/    _/  _/    _/  _/    _/
 _/_/_/    _/_/_/    _/_/_/
```

easy to use functions like javascript.

## ex.

```cpp
// ignore `const &`
bbb::opt_arg_function<void(const std::string &)> f = [](std::string str) { std::cout << str << std::endl; };

// call with extra arguments (will be discard)
f("hoge", 1, 2, 3, "blah", "brah", "blur");

// convert from function need few arguments. (discard args when call it)
f = [] { std::cout << "foo" << std::endl; };
f("this arg will discards");

// convertible type (but sometime you will get warning now...)
bbb::opt_arg_function<void(int)> g = [](float x) { std::cout << x << std::endl; };

// convert to std::function
std::function<void(int)> h1 = g;
// explicitly
std::function<void(int)> h2 = g.as<void(int)>();

// convert to std::function with extra arguments (extra arguments will discard)
std::function<void(int, int, float)> i = g;
```

## License

MIT License.

## Author

* ISHII 2bit [bufferRenaiss co., ltd.]
* ishii[at]buffer-renaiss.com

## At the last

Please create a new issue if there is a problem.

And please throw a pull request if you have a cool idea!!

If you get happy with using this addon, and you're rich, please donation for support continuous development.

Bitcoin: `17AbtW73aydfYH3epP8T3UDmmDCcXSGcaf`
