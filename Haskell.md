## Basic knowledges
## 编译运行Haskell代码的步骤
1. 在终端输入 `. /Users/apple/.ghcup/env`
2. 再输入 `ghci` 开启
3. 如果要运行文件，则输入 `:l 文件名` (这里是字母`l`不是`|`)
4. 再调用文件内的函数即可
- `eg`
  ![本地图片]([1.jpg](https://github.com/ddggss/Haskell/blob/main/images/1.jpg) "example1")

## Types 
### `:type + expression`：显示表达式的类型
- `eg: :type not False`    ---> `not False : : Bool`

### Basic types 基本类型
- `Bool`      ---- 逻辑值
- `Char`      ---- 单个字符
- `String`    ---- 字符序列
- `Int`       ---- 固定精度整数
- `Integer`   ---- 任意精度整数
- `Float`     ---- 浮点数

### List types
A list is a sequence of values of the same type:
- `eg: [False, True, False] : : [Bool]`
- `eg: ['a','b','c','d'] : : [Char]`

### Tuple types
A tuple is a sequence of values of different types:
- `eg: (False, True) : : (Bool, Bool)`
- `eg: (False, 'a', True) : : (Bool, Char, Bool)`
- `eg: (True, ['a','b']) : : (Bool, [Char])`

## Functions
Function is a mapping from values of one type to values of another type
- `E.g. even : : Int -> Bool`

### Curried functions 柯里化函数
允许我们将一个多参数的函数分解为一系列只接受一个参数的函数。
- `eg: add : : (Int, Int) -> Int`
  - `add (x, y) = x+y`                   ----- 函数定义
  - `add (3,5) = 8`                        ----- 函数调用

### Polymorphic functions 多态函数
这种类型的function包含一个或多个类型的变量
- `eg: length : : [a] -> Int`

#### Examples
- `Length : : [a] -> Int`
  - `eg: length [False, True]`     ----- `a = Bool`
    - 输出: `2`
  - `eg: length [1,2,3,4]`            ----- `a = Int`
    - 输出: `4`

### Overloaded functions
如果一个polymorphic function被称为overloaded, 那么这个function包含一个或多个类限制
- `eg: (+) : : Num a => a --> a --> a`

## Type classes
- `Num`    -- Numeric types
- `Eq`     -- Equality types
- `Ord`    -- Ordered types

## Defining Functions
### Conditional expressions
- `eg: abs : : Int -> Int`
  - `abs n = if n>= 0 then n else -n`

### Guarded equation
- `eg: abs n | n >= 0 = n`
  - `| otherwise = -n`

### Pattern matching

### List Pattern

### Lambda Expressions
- `a. 定义: \parameters -> expression`
  - `\` 表示匿名函数
  - `parameters` 是参数列表
  - `->` 表示参数的结束和函数体的开始
  - `expression` 是函数体

### Operator Sections
- `a. Prefix section 前缀形式`
  - `(+3)`    ---- 创建一个函数, 它接受一个参数并返回该参数与3的和

- `b. Postfix section 后缀形式`
  - `(3+)`    ---- 它期望一个参数，并将该参数加到3上

## Lists comprehensions
### List
- `a. 由一个generator或多个generators构成, 逗号进行分割`

### Concatenates list
- `a. concat : : [[a]] ---> [a]`
  - `eg: concat [[1,2,3], [4,5], [6]]`          输出: `[1,2,3,4,5,6]`

### Guards
- `a. factors : : Int ---> [Int]`
  - `factors n = [x | x <--- [1..n], n 'mod' x == 0]`

### Zip function
- `a. zip : : [a] ---> [b] ---> [(a,b)]`
  - `eg: zip ['a', 'b', 'c'] [1,2,3,4]`             输出: `[('a',1), ('b', 2), ('c', 3)]`

## Recursive function

