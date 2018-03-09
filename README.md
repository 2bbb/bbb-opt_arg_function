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

* ignore `const &`

```cpp
bbb::opt_arg_function<void(const std::string &)> f = [](std::string str) { std::cout << str << std::endl; };
```

* discard arg with no parameter

```cpp
f = [] { std::cout << "foo" << std::endl; };
```

* call with extra arguments

```cpp
f("hoge", 1, 2, 3, "blah", "brah", "blur");
```

* convertible type (but you will get warning now...)

```cpp
bbb::opt_arg_function<void(int)> g = [](float x) { std::cout << x << std::endl; };
```

* convert to std::function

```cpp
std::function<void(int)> h = g.as<void(int)>();
```

* convert to std::function with extra arguments (extra arguments will discard)

```cpp
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