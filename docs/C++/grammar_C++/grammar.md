# C++语法

## 关键字

```
asm       auto      bool      break     case      catch
char      class     const     const_cast    continue  default
delete    do        double    dynamic_cast  else      enum
explicit  export    extern    false     float     for
friend    goto      if        inline    int       long
mutable   namespace new       noexcept  nullptr   operator
private   protected public    register  reinterpret_cast   return
short     signed    sizeof    static    static_cast    struct
switch    template  this      throw     true      try
typedef   typeid    typename  union     unsigned  using
virtual   void      volatile  wchar_t   while
```
### using

- 类型别名
```
using MyInt = int;
MyInt x = 42;
```

- 函数指针别名
函数指针是指向函数的指针变量
C++中函数也是一种数据类型，可以像整数、浮点数一样在程序中进行传递、存储和操作。函数指针用于存储和调用函数的地址。
函数指针声明
```
return_type (*function_pointer_name)(parameter_types);
```
例
```
int (*add)(int, int);
```
函数指针是指向函数的指针变量。在C++中，函数也是一种数据类型，可以像整数、浮点数一样在程序中进行传递、存储和操作。函数指针用于存储和调用函数的地址。

函数指针的声明通常如下所示：

```cpp
return_type (*function_pointer_name)(parameter_types);
```

- `return_type` 是函数的返回类型。
- `function_pointer_name` 是函数指针的名称。
- `parameter_types` 是函数的参数类型。

例如，以下是一个函数指针的声明示例：

```cpp
int (*add)(int, int);
```

这个函数指针 `add` 可以指向一个接受两个整数参数并返回整数的函数,可以将函数的地址分配给函数指针，然后通过函数指针调用该函数，就像调用普通函数一样。


```
using MyFunctionPointer = int(*)(int, int);
```


