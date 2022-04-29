# ReduxToolkit-use
替代redux的工具ReduxToolkit的基本使用

## 使用createSlice注意
1. 首先，Redux 操作类型并不意味着对单个切片是专有的。从概念上讲，每个 slice reducer “拥有”自己的 Redux 状态，但它应该能够监听任何动作类型并适当地更新其状态
例如，许多不同的切片可能希望通过清除数据或重置回初始状态值来响应“用户注销”操作。在设计状态形状和创建切片时请记住这一点。

2. 其次，如果两个模块尝试相互导入，JS 模块可能会出现“循环引用”问题。这可能导致导入未定义，这可能会破坏需要导入的代码。特别是在“鸭子”或切片的情况下，如果两个不同文件中定义的切片都希望响应另一个文件中定义的操作，则可能会发生这种情况。

当切片A和切片B同时拥有相同类型的action 则会同时触发 可以从引入其他切片的action
[栗子](https://codesandbox.io/s/rw7ppj4z0m)
