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


`return_type` 是函数的返回类型。
`function_pointer_name` 是函数指针的名称。
`parameter_types` 是函数的参数类型。

例如，以下是一个函数指针的声明示例：

```
int (*add)(int, int);
```

这个函数指针 `add` 可以指向一个接受两个整数参数并返回整数的函数,可以将函数的地址分配给函数指针，然后通过函数指针调用该函数，就像调用普通函数一样。
函数名为函数地址
```
int addNumbers(int a, int b) {
    return a + b;
}

int main() {
    // 声明一个函数指针
    int (*functionPtr)(int, int);
    
    // 将函数的地址分配给函数指针
    functionPtr = addNumbers;
    
    // 使用函数指针调用函数
    int result = functionPtr(5, 3); // 调用 addNumbers 函数
    std::cout << "Result: " << result << std::endl;
    
    return 0;
}
```

```
using MyFunctionPointer = int(*)(int, int);
```

- 模板别名
- 命名空间别名
- 成员函数别名
- 枚举别名

### typename
- 声明模板类型参数
```
template <typename T>
```
声明一个通用类型参数T，可接受不同类型的参数




### template
用于创建通用的函数和类,可避免反复声明参数类型

## 类
类是一种自定义的数据类型，用于封装数据（成员变量）和操作数据的方法（成员函数）
- 对象 
类的实例被称为对象
- 成员变量 
类中用于存储数据的变量
- 成员函数
类中定义的用于执行操作的函数
- 封装
将数据和方法绑定在一起，类通过将成员变量和成员函数组合在一起，将数据和操作数据的代码封装在一个单独的单元中
- 继承
一个类可以继承另一个类的属性和方法，继承允许在不重复编写相似代码的情况下创建新类
- 多态
多态是一种能力，允许不同类的对象对相同的方法做出不同的响应。这使得可以使用基类的指针或引用来调用派生类的方法
